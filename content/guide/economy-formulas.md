---
title: "Economy Formulas"
date: 2026-07-02
draft: false
description: "Precise game formulas for power users"
weight: 20
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

For players who want to optimize every credit. These are the live formulas as of v1.22.0, verified against the game backend. Numbers can shift in future releases — check the version stamp.

One rhythm underpins most of them: the **4-hour cycle**. Turn resets, planet production, disabled-ship recovery, trade-pressure recovery, and trading post refills all run at 00/04/08/12/16/20 UTC.

## Trade Prices

Each port type charges a fixed base price per commodity — identical in every galaxy. Stock level has no effect on price.

```
buyPrice  = basePrice[portType][commodity]
sellPrice = floor(buyPrice × 0.9)
```

**Base buy prices (cr/unit):**

| Port Type | Fuel | Organics | Equipment |
|-----------|------|----------|-----------|
| Stardock | 100 | 120 | 500 |
| Federation Port | 120 | 140 | 600 |
| Standard Port | 90 | 110 | 450 |
| Fuel Depot | 70 | 180 | 500 |
| Agricultural Station | 130 | 60 | 700 |
| Tech Outpost | 110 | 130 | 300 |
| Pirate Base | 80 | 100 | 400 |
| Black Market | 60 | 80 | 200 |
| Mining Station | 85 | 200 | 450 |
| Research Complex | 120 | 150 | 280 |

Two live modifiers apply on top, in order:

**Trade pressure** (standard-economy ports only — Standard, Fuel Depot, Agricultural, Tech, Mining, Research):

```
buyPrice'  = floor(buyPrice × (1 + B × 0.002))          // no ceiling
sellPrice' = max(1, floor(sellPrice × (1 − S × 0.002))) // floor 1 cr
```

B and S are per-commodity **transaction** counts (buys and sells). Pressure decays 20 points per 4-hour cycle, but only for commodities with zero trades during that cycle.

**Reputation:**

```
buyPrice''  = buyPrice'  × factionMult × traderMult
sellPrice'' = sellPrice' × 1 / (factionMult × traderMult)
```

factionMult ranges 0.80 (friendly) to 1.50 (hostile), linear over ±1000 alignment, at Federation and Pirate ports only. traderMult ranges 0.90 to 1.10 over trader reputation 0–100. See [Reputation & Factions](/guide/reputation-factions/).

**Fees and taxes** (per transaction):

```
buyTotal  = subtotal + round(subtotal × taxRate) + round(subtotal × 0.01)
sellTotal = subtotal − tax − portFee
```

taxRate: Federation 5% (7% for Pirate-faction players), Tech Outpost 3%, everything else 2% (player trading posts: 0% when you buy, 2% when you sell). The 1% port fee applies everywhere.

## Ship Combat

Full context in the [Combat guide](/guide/combat/). Attack and defense are asymmetric — fighters and torpedoes only attack, shields only defend:

```
attackPower  = basePower × 0.5 + 2.0 × fighters + 5.0 × torpedoes
defensePower = basePower × 0.5 + 3.0 × shields
```

**Torpedo shield penetration:** each attacker torpedo bypasses 1% of the defender's shield contribution, capped at 50%:

```
defensePower −= 3.0 × shields × min(0.50, torpedoes × 0.01)
```

**Modifiers** (multiply the relevant side's power):

| Modifier | Effect |
|----------|--------|
| Ship role | offense/defense multipliers roughly 0.95–1.12 by class |
| Ship tier | +4% per tier above 1 (max +16% at Tier 5) |
| Advanced Attack Systems | +10% offense |
| Reinforced Armor Plating | +10% defense |
| Combat AI Core | fighters count ×1.20 |
| Region: FED_CORE / FED_SPACE | +10% / +5% to Federation-aligned defenders |
| Region: MIDDLE / OUTER | +2% / +5% to any attacker |
| Region: OUTER_RIM | +10% to pirate-aligned ships (either role) |

**Win probability:**

```
p = A × U[0.98, 1.02] / (A × U + D × U)
  + 0.30 × (atkFighters / (atkFighters + defFighters + 1) − 0.5)   // ±15% max
  + stealth first-strike (+12%, −6% if defender has sensors)
p clamped to [0.05, 0.95];  attacker wins if rand() < p
```

No fight is ever safer than 95% or more hopeless than 5%.

**Combat is pre-rolled.** NPC encounter outcomes are computed the moment the encounter fires — pressing Attack on a non-aggressive NPC commits an already-decided result, and an ambush is applied before you even see the modal.

**Retreat** (defending players only, rolled before any power math):

```
escape = 0.25 + 0.35 × escapeRating − 0.15 × (atkFighters / totalFighters)
         (+0.05 in FED_CORE/FED_SPACE) (+0.15 Stealth Plating) (+ship-ability escape bonuses)
clamped to [0.05, 0.85]
```

**Attrition.** With `a = (1 − p) × (1 − shields/(shields + 100) × 0.5)`:

```
Winner: fighters −= floor(fighters × a × 0.4)
        shields  −= floor(shields × a × 0.25)
        torps    −= floor(torps × (0.2 + 0.5 × a))
Loser:  loses (0.5 + 0.5 × p) × own shield mitigation, applied to all three stats
```

The loser is always **disabled** (not destroyed, unless it entered the fight with 0 shields, 0 fighters, and 0 torpedoes — then it's destroyed). Disabled ships auto-repair at the next 4-hour boundary: status OK, shields restored to 50% of max. Fighters and torpedoes are consumables — re-buy them at a starport, or use port repair to restore everything.

## Siege (Port & Planet Attacks)

Attacks on ports and planets use a separate, simpler formula — this is where the old 0.8/1.2/2.0 weights live:

```
A = ceil(fighters × 1.2 if Combat AI) × 0.8 + shields × 1.2 + torpedoes × 2.0
D = max(10, garrison × 0.8 × (1 + defenseBonus) + structuralDefense)
p = clamp01(A / (A + D) ± 0.02)
```

For planets, defenseBonus combines Shield and Citadel structures multiplicatively: defenseBonus = (1 + 0.15 × shieldLevel) × (1 + 0.10 × citadelLevel) − 1 (so 5/5 gives +158.75%, not +125%), and structuralDefense = 12 × shieldLevel + 25 × citadelLevel. Win: garrison −50%. Loss: garrison −20%, your ship disabled with fighters and shields wiped.

## Loot

Winner takes credits from the loser's **wallet** — banked credits are never touched:

```
creditsLooted = floor(min(tierCap, loserWallet × lootFactor))
```

**Loot factors by the winner's faction:**

| Winner Faction | Credits | Cargo |
|----------------|---------|-------|
| Neutral | 25% | 30% |
| Federation | 20% | 25% |
| Pirate | 35% | 40% |

**Credit caps by the winner's ship tier:**

| Tier | Credit Cap |
|------|-----------|
| 1 | 5,000 cr |
| 2 | 15,000 cr |
| 3 | 40,000 cr |
| 4 | 100,000 cr |
| 5 | 200,000 cr |

In **PvP, loot is credits only** — cargo is not transferred between players. When an **NPC defeats you**, it also takes cargo (the cargo factor of what you carry), deducted from your cheapest lots first; contraband lots are never looted.

## Planet Production

Runs every 4-hour cycle (6 ticks per day). Uncollected output does not accumulate — the next tick overwrites it. Full context in the [Planets guide](/guide/planets/).

```
factoryMult = 1 + 0.15 × factoryLevel
popMult     = 0.2 + (population / populationCap) × 0.8
citadelMult = 1 + 0.10 × citadelLevel

output[c] = floor(base[c] × factoryMult × popMult × citadelMult)
```

**Base rates per tick:** Fuel 35, Organics 25, Equipment 13. A maxed planet (Factory 5, Citadel 5, full population) produces 91 fuel + 65 organics + 34 equipment = 190 units per tick. Planet type and location have no effect on production.

**Export income** is paid automatically every tick, straight to your bank:

```
exportCredits = round(totalUnitsProduced × 30)
```

A maxed planet earns about 5,700 cr per tick — roughly 34,000 cr per day — on top of the goods themselves.

**Population growth (per tick):**

```
growth = floor(10 × (1 + 0.10 × habitatLevel) − floor(population × 0.01))
newPopulation = min(population + growth, populationCap)
```

The 1% attrition means natural growth stalls before the cap on upgraded Habitats — ship in Mining Workers to top out.

**Garrison cap** (also caps deployed sector fighters):

```
cap = floor(500 × 2^citadelLevel)     // 500 → 16,000 at Citadel 5
```

Barracks add 4 × level free garrison fighters per tick, up to the cap.

## Structure Upgrade Costs

```
cost = floor(baseCost × multiplier^(level − 1))    // level = the level being bought
```

| Structure | Base Cost | Multiplier | Effect per Level |
|-----------|-----------|------------|------------------|
| Warehouse | 5,000 cr | 1.8× | +2,000 storage |
| Habitat | 6,000 cr | 1.8× | +250 population cap, +10% growth |
| Factory | 7,500 cr | 1.8× | +15% production |
| Barracks | 7,500 cr | 1.9× | +4 garrison fighters/tick |
| Shield Generator | 10,000 cr | 2.0× | +15% siege defense, +12 structural |
| Citadel | 25,000 cr | 2.0× | +10% production & defense, +25 structural, garrison cap ×2 |

All six structures max at level 5. The **Citadel requires Factory 3 and Shield 3** before you can build it.

**Factory ladder (typical of the 1.8× structures):**

| Level | Level Cost | Cumulative |
|-------|-----------|------------|
| 1 | 7,500 | 7,500 |
| 2 | 13,500 | 21,000 |
| 3 | 24,300 | 45,300 |
| 4 | 43,740 | 89,040 |
| 5 | 78,732 | 167,772 |

Fully maxing all six structures costs about 1.7 million credits, plus the 150,000 cr claim.

## NPC Spawn Rates

One roll per sector move (types tried in priority order Pirate → Patrol → Trader; at most one NPC spawns per move):

```
P(type) = baseRate × regionMultiplier
```

**Base rates:** Pirate 3%, Trader 2%, Patrol 1.5%.

**Region multipliers:**

| Region | Pirate | Trader | Patrol |
|--------|--------|--------|--------|
| FED_CORE | 0× | 1.5× | 4.0× |
| FED_SPACE | 0× | 1.5× | 3.5× |
| INNER | 0.4× | 1.8× | 1.5× |
| MIDDLE | 1.0× | 2.0× | 0.8× |
| OUTER | 1.5× | 0.5× | 0.1× |
| OUTER_RIM | 2.0× | 0.3× | 0× |

Territory adds hard blocks regardless of region: pirates never spawn in Federation territory, patrols never spawn in pirate territory. Per-sector caps: 2 patrols, 3 pirates, traders unlimited. Warp hops roll at min(5% per hop, capped at ~30% for the whole journey). See [NPCs](/guide/npcs/).

## Contraband Detection

Two separate systems. Full context in [Smuggling](/guide/smuggling/).

**Entry scans** (Federation port customs and patrol scans):

```
threshold = 75%
with Goods Cloaking Device:  25%   (one device consumed per scan, caught or not)
Stealth Hull Plating:        −30 points, floor 5%
```

| Mitigation | Catch Chance |
|------------|-------------|
| None | 75% |
| Stealth Plating only | 45% |
| Cloaking Device only | 25% |
| Device + Plating | 5% |

Scans are skipped entirely if you carry no contraband or your alignment is above +300. Port customs scans fire when you open the trade screen at a Federation port, on a 30-minute cooldown (the cooldown gates customs only — patrol scans always run when you submit). If customs catches you: all contraband seized galaxy-wide, fine = 10% of its value (capped at your wallet), −5 alignment. A patrol scan bust seizes contraband and costs −5 alignment but carries no fine — the only patrol fine is a flat 2,000 cr when a failed bribe's forced scan catches you.

**Sale-time detection** (rolled when you sell a contraband lot):

```
p = regionBase                          // FED_CORE 22%, FED_SPACE 18%, INNER 12%,
                                        // MIDDLE 8%, OUTER 3%, OUTER_RIM 1%
  + criminal alignment bonus            // up to +25 points at −1000
  + cargo fullness                      // up to +20 points when holds are full
  − 30 points with Stealth Hull Plating
  − ship stealth/smuggler abilities
```

A detected sale is simply **blocked** — no fine, no seizure, no turn spent — and you can retry immediately. Cloaking Devices do not affect this roll.

## Tech Upgrade Effects

The Tech Hub catalog is exactly 7 items (sold at Stardock and Tech Outpost ports; see [Tech Upgrades](/guide/tech-upgrades/)):

| Upgrade | Effect |
|---------|--------|
| Cargo Compressors | holds += floor(maxHolds × 0.20), computed at purchase time |
| Shield Booster Arrays | max shields += floor(currentShields × 0.15) |
| Combat AI Core | fighters count ×1.20 in all combat |
| Stealth Hull Plating | −30 points on both detection systems; +15% escape chance when defending |
| Warp Drive Optimizer | warp turn cost −1 (min 1); does not apply to Tesseract jumps |
| Advanced Attack Systems | +10% combat offense |
| Reinforced Armor Plating | +10% combat defense |

Two order-of-purchase quirks worth exploiting:

- **Cargo Compressors** scale off your max holds at purchase time — buy them *after* your cargo hold tiers for the biggest bonus.
- **Shield Booster Arrays** compute from your *current* shields, not max — repair to full before buying, or the smaller bonus is permanent.
