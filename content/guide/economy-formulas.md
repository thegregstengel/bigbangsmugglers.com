---
title: "Formulas & Numbers"
date: 2026-08-04
description: "Every constant on one page, current season defaults"
weight: 21
group: numbers
tags: [platform]
changed_in: [2.3.0, 2.0.16]
---

Everything on this page is a **current season default**. Almost every number
here is season configuration and can be retuned between seasons — or
mid-season by the operators — without a client update. Where a rule is
structural rather than tunable, it says so.

If a number here disagrees with what the game shows you, **the game is
right** and this page is stale. Tell us.

---

## Turns

| Knob | Default |
|---|---|
| Turn cap | 250 |
| Cycle length | 4 hours |
| Cycle boundaries | 00:00, 04:00, 08:00, 12:00, 16:00, 20:00 UTC |
| Carryover | None, ever — doctrine, not a knob |
| Provision price | 800 cr per turn |
| Provision ration | 5 turns per cycle |

### Turn costs

| Action | Turns |
|---|---|
| Move to a linked sector | 1 |
| Wormhole transit | 1 |
| Buy or sell cargo (one leg) | 1 |
| Buy or sell contraband | 1 |
| Engage in combat | 1 |
| Fleet strike | 1 |
| Trade with a trader NPC (per deal) | 1 |
| Rob a trader NPC | 1 |
| Deploy ordnance | 1 |
| Attack ordnance | 1 |
| Destroy a foreign beacon | 1 |
| Lay mines from a planet garrison | 1 |
| Active scan | 1 per ring (radius 1–3) |
| Warp jump | `max(1, ceil(hops ÷ warpLevel))` |
| Tesseract jump | 25, flat |
| Port siege attack | 3 |
| Capture or raze a port | 1 |
| Claim a planet | 1 |
| Build or upgrade a structure | 1 |
| Raid or capture a planet | 1 each |
| Port repair | 0 |
| Landmark interaction | 0 |
| Banking, limpets, beacons, vault, planet storage, claim redemption | 0 |

Warp Optimizer (−1) and the Explorer role (−1 to −3) stack, floor at 1 turn,
and **never** apply to the Tesseract.

---

## The market

### Price model

```
deviation  = (baseline − stock) ÷ baseline                when stock ≤ baseline
           = −(stock − baseline) ÷ (max − baseline)       when stock > baseline
swung      = anchor × (1 + 0.28 × deviation)
pressure   = 1 + min(1.00, unitsTraded × 0.0001)
buy price  = floor(swung × pressure)
sell price = floor(swung ÷ pressure × 0.90)
```

| Knob | Default |
|---|---|
| Max stock swing | ±28% |
| Sell factor | 0.90 |
| Pressure per unit | 0.0001 |
| Pressure cap | ×2.00 |
| Pressure decay | 1,000 units per idle tick |
| Port fee | 1%, both directions |
| Restock per tick | `ceil(gap to baseline × rate)` |

Restock rate: **1.00** at the Stardock and Merchant Exchange, **0.50** at the
Pirate Haven, **0.15** everywhere else.

**Structural:** after every modifier and every rounding step, a port's sell
price is strictly below its buy price for the same player at the same market
state. No configuration can invert it.

### Anchors and pool depth

Anchor (cr/unit) / maximum stock. Asterisk = buy-only.

| Archetype | Fuel | Organics | Equipment |
|---|---|---|---|
| Stardock | 125 / 1M | 150 / 1M | 625 / 1M |
| Merchant Exchange | 110 / 2M | 130 / 2M | 520 / 2M |
| Federation Port | 150 / 50k | 170 / 30k | 750 / 40k |
| Trading Port | 115 / 20k | 135 / 15k | 550 / 18k |
| Fuel Depot | **90 / 80k** | 215 / 5k* | 600 / 10k* |
| Agricultural Port | 160 / 8k* | **75 / 60k** | 850 / 5k* |
| Tech Port | 135 / 5k* | 155 / 8k* | **375 / 50k** |
| Mining Port | 105 / 25k | 240 / 2k* | 550 / 15k |
| Research Port | 145 / 8k* | 185 / 3k* | **350 / 30k** |
| Pirate Base | 100 / 15k | 125 / 12k | 500 / 25k |
| Black Market | 80 / 3k | 100 / 5k | 300 / 15k |
| Pirate Haven | 100 / 60k | 125 / 50k | 500 / 100k |

Starting stock — which is also the baseline the price swings around — is
**50% of maximum** for commodities the port sells, **25%** for buy-only rows.

### Taxes

| Archetype | Tax |
|---|---|
| Fuel Depot | 1% |
| Stardock, Trading Port, Mining Port | 2% |
| Tech Port | 3% |
| Agricultural Port | 4% |
| Federation Port | 5% (**7%** for Pirate-aligned players) |
| Research Port | 5% |
| Merchant Exchange | 0.5% |
| Pirate Base, Black Market, Pirate Haven | 0% |

A corp-held port charges its members `tax × 0.5` and everyone else `tax + 1pp`.
Trader role tiers subtract up to 2pp, floored at 0.

```
buy total   = subtotal + floor(subtotal × tax) + floor(subtotal × fee)
sell payout = subtotal − floor(subtotal × tax) − floor(subtotal × fee)
```

### Cargo volume

| Commodity | Volume |
|---|---|
| Fuel | 1 |
| Organics | 1 |
| Equipment | **2** |

---

## Ships

### Tier ladder

| Tier | Cost | Ladder gate (fraction of the season ladder) | Shields (neutral/pirate) | Shields (Federation) |
|---|---|---|---|---|
| 1 | 5,000 | — | 150 | 165 |
| 2 | 15,000 | early (~8%) | 225 | 250 |
| 3 | 40,000 | ~22% | 350 | 385 |
| 4 | 100,000 | ~43% | 525 | 580 |
| 5 | 250,000 | ~two-thirds | 800 | 880 |

Tier gates are pinned per season as a level **and** the matching XP total on
that season's curve; the shipyard quotes both and they always agree.

### Base stats by archetype (T1 → T5)

| Archetype | Holds | Fighters | Torpedoes | Hull | Hull ×|
|---|---|---|---|---|---|
| Trading / Smuggling / Patrol | 60, 90, 140, 210, 320 | 13, 20, 29, 42, 65 | 7, 10, 16, 23, 35 | 80, 120, 180, 272, 400 | 0.80 |
| War / Raider / Enforcer | 25, 35, 50, 75, 110 | 33, 49, 75, 114, 172 | 17, 26, 40, 61, 93 | 125, 187, 281, 425, 625 | 1.25 |
| Balanced / Corsair / Dreadnought | 40, 60, 90, 135, 200 | 23, 33, 49, 75, 114 | 12, 17, 26, 40, 61 | 100, 150, 225, 340, 500 | 1.00 |

Tier base hull before the multiplier: `[100, 150, 225, 340, 500]`.

**SS Starter:** 20 holds, 15 shields, 40 hull, 0 fighters, 0 torpedoes, 0.30
escape.

### Escape ratings

| Line | Trading role | War role | Balanced role |
|---|---|---|---|
| Neutral | 0.30 | 0.40 (0.30 at T5) | 0.50 |
| Federation | 0.30 | 0.40 (0.30 at T5) | 0.50 |
| Pirate | 0.40 | 0.50 (0.40 at T5) | 0.60 |

### Upgrade caps

Total purchasable gain as a fraction of base:

| Archetype | Holds | Shields | Fighters | Torpedoes |
|---|---|---|---|---|
| Trading / Smuggling / Patrol | +100% | +50% | +100% | +100% |
| War / Raider / Enforcer | +50% | +50% | +200% | +200% |
| Balanced / Corsair / Dreadnought | +80% | +50% | +160% | +160% |

**Holds:** gains 30 / 20 / 20 / 15 / 15% of the total at cost multipliers
×8 / 16 / 40 / 100 / 300 of the hull's hold base cost.
**Combat stats:** cumulative 25 / 45 / 60 / 70 / 80% of the shape at
×8 / 16 / 28 / 44 / 64.

### Services

| Service | Price |
|---|---|
| Trade-in | 64% of purchase price |
| Rename | 1,000 cr |
| Restock a fighter | 75 cr |
| Restock a torpedo | 150 cr |
| Repair a shield point | 5 cr |
| **Repair a hull point** | **8 cr** |
| Repair minimum | 200 cr |
| Limpet sweep | 10,000 cr, charged even when clean |

Repair covers **shields and hull only**. Shields regenerate free to exactly
50% of maximum at each world tick for any ship below 50%. **Hull never
regenerates.**

### Drives

| Drive | Install | Upgrade | Gates |
|---|---|---|---|
| Warp | 15,000 | 15,000 × level, to L5 | Tier 2+ hull, an early ladder gate |
| StarNav 2002 | 100,000 | 100,000 × next level (L5 = 500k) | Per-level ladder gates, mid-early at L1 to ~two-thirds at L5 |
| Tesseract | 10,000,000 | — | Tier 5 hull, **the top gate of the ladder** |

> Whether a season's ladder reaches the Tesseract's gate is that season's
> tuning: 50-ladder seasons created before the migration cap out below it,
> and it never unlocks there. New seasons place it near the top of a
> 100-level ladder. The in-game unlock list is authoritative.

### StarNav detail table

| Level | 1 hop | 2 hops | 3 hops |
|---|---|---|---|
| 1 | empty | — | — |
| 2 | empty | empty | — |
| 3 | POI | empty | empty |
| 4 | full | POI | empty |
| 5 | full | full | POI |

Range is `min(level, 3)`. Cloak reveal at effective StarNav **4**; deployables
report at StarNav **2**.

### Tech modules

All modules are level-gated (utility modules early, stealth/faction modules
deeper — the shop shows your season's numbers).

| Module | Cost | Effect |
|---|---|---|
| Cargo Compressors | 8,000 | +20% of base holds |
| Shield Booster | 10,000 | +15% of base shields |
| Attack Systems | 12,000 | +10% attack |
| Armor Plating | 12,000 | +10% defense |
| Combat AI | 15,000 | +20% fighter effectiveness |
| Advanced Sensors | 15,000 | Halves a stealth first strike |
| Warp Optimizer | 18,000 | −1 warp turn |
| Stealth Plating | 15,000 | −30pp customs scan, +15pp escape, +12pp first strike |
| Patrol Transponder | 20,000 | Federation only — no patrol encounters |
| False Manifest | 20,000 | Pirate only — one failed scan/day rerolls |

---

## Combat

| Constant | Value |
|---|---|
| Fighter attack / defense weight | 2.0 / 1.0 |
| Shield attack / defense weight | 0 / 3.0 |
| Torpedo attack / defense weight | 5.0 / 0 |
| Base power | hull tier × 100, halved into the sum |
| Drizzle | ×0.98–1.02 per side |
| Win probability clamp | 5% – 95% |
| Fighter skirmish swing | ±30% on fighter share |
| Torpedo shield penetration | 1% per torpedo, max 50% |
| Stealth first strike | +12pp (−6pp vs Advanced Sensors or sensor edge) |
| **Hull spill multiplier** | **×1.5** |
| Winner fighter attrition | 40% |
| Winner shield attrition | 25% |
| Torpedo consumption | 20% + 50% × attrition |
| Loser minimum loss rate | 50% |
| Defeat loss rate (sieges, ordnance) | 75% |
| Shield damage reduction | up to 50%, scaling on shields ÷ (shields + 100) |
| **PvP immunity** — defender attacked (win or lose), attacker's loss, any death | **2 minutes** |
| Defense contract | 4,000 cr / 2 hours, stacking |
| XP tier multiplier | ×0.95 to ×1.20 |
| Faction combat bonus cap | +5% |

### Escape

```
chance = 0.25
       + 0.35 × escapeRating
       − 0.15 × attackerFighterShare
       + 0.05  Federation space
       + 0.05–0.08  Corsair retreat signature
       + 0.15  Stealth Plating
       + 0.10  asteroid field
clamped to [5%, 85%]
```

### Region combat modifiers

| Region | Effect |
|---|---|
| `fed_core` | Federation-aligned defenders +10% |
| `fed_space` | Federation-aligned defenders +5% |
| `middle` | Attackers +2% |
| `outer` | Attackers +5% |
| `outer_rim` | Pirate-aligned +10% |

### Loot on a PvP win

| Winner's alignment | Credits | Cargo |
|---|---|---|
| Federation (≥ +300) | 20% | 25% |
| Neutral | 25% | 30% |
| Pirate (≤ −300) | 35% | 40% |

Credit cap by hull tier: 5,000 / 15,000 / 40,000 / 100,000 / 200,000.
**Wallet only — the bank is never looted.** Defenders who win loot too
(since v2.3.0).

### Alignment from combat

| Situation | Win | Loss |
|---|---|---|
| Attacked a Federation-aligned player | −8 | −3 |
| Attacked a neutral player | −2 | −1 |
| Fought a Pirate-aligned player | +6 | +2 |
| Attacked Federation forces (NPC) | −6 | −2 |
| Attacked a neutral trader (NPC) | −1 | 0 |
| Fought pirate raiders (NPC) | +4 | +1 |
| **Defended against a pirate and survived** | **+2 defender** | — |

### Hazards

| Hazard | Arrival chance | Damage | In combat |
|---|---|---|---|
| Asteroid field | 20% | 10–20 | +10pp escape, −10% torpedo penetration |
| Radiation zone | 100% | 25 | −10% shield defense |
| Minefield | 40% | 40–60 | — |
| Ion storm | 100% | — | −20% to every tech module bonus |
| Nebula | 100% | — | −15% fighter effectiveness |

Warp pass-through rolls at **25%** of the arrival chance. Wormhole transit is
exempt.

---

## Ordnance and limpets

| Item | Price | Volume | Sector cap | Your cap | Attack | Defense | Lifetime |
|---|---|---|---|---|---|---|---|
| Proximity Mine | 250 | 2 | 100 (+50 where you own a planet) | 500 | 8 | 0 | 2%/day decay |
| Sentry Drone | 1,500 | 8 | 50 | 20 | 5 | 3 | 3%/day |
| Turret | 3,000 | 15 | 20 | 8 | 12 | 2 | 3%/day |
| Sensor Buoy | 800 | 3 | 10 | 5 | 0 | 1 | 1%/day |
| Cloak Field | 5,000 | 10 | 1 | 2 | 0 | 0 | 48h |
| Limpet Tracker | 4,000 | — | — | 10 live | — | — | 48h once attached |
| Navigation Beacon | 2,500 | — | one per player per sector | — | — | — | — |

Mines: **60%** to fire per mine, at most **3** per entry, `attack × 4–6`
damage each. Ordnance attack: `power ÷ (power + ordnancePower) ± 20%`,
clamped 5–95%. No-deploy in `fed_core` and `fed_space`.

### Other items

| Item | Price | Service |
|---|---|---|
| Goods Cloaking Device | 750 | blackmarket |
| Ship Cloaking Device | 2,500 | blackmarket |
| Security Personnel | 100 | recruitment |
| Mining Workers | 300 | recruitment |

Per-purchase caps were dropped in v2.0.16 (they never limited anything); a
10,000-unit single-order ceiling remains as a typo guard, not a game rule.

Ship cloak duration: **2 hours**, fixed from activation.

### Mercenary retinues

| Tier | PvE bonus | Hire fee | Wage per tick |
|---|---|---|---|
| Escort Wing | +4% | 2,000 | 250 |
| Veteran Wing | +8% | 8,000 | 750 |
| Elite Wing | +12% | 25,000 | 2,000 |

One contract at a time; each tier behind its own ladder gate. Wages draw
from the **wallet** each world tick — an uncovered wage deserts before
charging. Desertion on PvE defeat; hard cap 12 ticks (48 h). Bonus applies
at NPC-opponent sites only — never PvP, never sieges. Hiring: stardock =
Federation Auxiliary; pirate bases and the Haven = Cutthroat Company;
each line refuses the hostile ±300 bucket.

### Trader NPC interactions

| Knob | Default |
|---|---|
| Buy price | standard anchor × **1.35** (guild band applies) |
| Sell price | standard anchor × **0.65** |
| Deals per trader per player | 3 |
| Manifest depth (T1/T2/T3 cap per commodity) | 20 / 60 / 150 |
| Contraband carry chance | 0 core → 35% `outer_rim`, always priced above the fence |
| Named (merchant prince) multiplier | ×5 manifest and loot, once per season |
| Rob yield chance | `clamp(winProb − 0.15, 0.05, 0.90)` |
| Rob cargo band (T1/T2/T3) | 5–15 / 15–40 / 40–100 units of one commodity |
| Rob consequences | −10 alignment, +5 × tier Syndicate, −25 Guild |
| Rob heat regions | `fed_core`, `fed_space`, `inner` → Federation bounty counter (princes ×2) |

---

## Factions and standing

| Knob | Default |
|---|---|
| Membership | ±500 |
| Elite content | ±750 |
| PvP classification / NPC aggression / docking | ±300 |
| Alignment bounds | ±1,000 |
| Member-tier standing | 1,000 |
| Standing decay | **1% per day** |
| Guild price band | −10% on buys, saturating at 1,000 standing |
| Alignment price band | −20% friendly buys / +50% hostile buys at ±1,000 |

### The benefit curve

| \|Alignment\| | Benefit |
|---|---|
| 500 | 2% |
| 600 | 3% |
| 750 | 4% |
| 900 | 5% |

Used identically for the combat bonus, the own-faction service discount, and
the standing card.

### Rank ladders

Thresholds 0 / 1,000 / 2,500 / 5,000 / 10,000.

| Faction | Ranks |
|---|---|
| Federation | Cadet, Lieutenant, Commander, Captain, Admiral |
| Syndicate | Crew, Quartermaster, First Mate, Captain, Pirate Lord |
| Merchant Guild | Peddler, Broker, Trader, Merchant, Magnate |

### Alignment tiers

Paragon ≥900 · Hero ≥750 · Champion ≥600 · Ally ≥500 · Law-Leaning >250 ·
True Neutral −250…250 · Chaos-Leaning <−250 · Rogue <−500 · Villain <−600 ·
Terror <−750 · Scourge ≤−900.

### Standing movement

| Deed | Standing |
|---|---|
| Kill an enemy-faction NPC | +15 × tier |
| Kill your own faction's NPC | −15 × tier |
| Capture a port in enemy space | +100 |
| Attack a faction's port | −15 |
| Honest trade leg | +1 Merchant Guild |
| Faction daily mission | +100 |
| Elite faction arc | +400 |

### Alignment movement outside combat

| Deed | Alignment |
|---|---|
| Pass a customs scan clean | +2 |
| Survive a pirate attacker | +2 |
| Claim a planet in aligned territory | ±250 |
| Siege an underworld port | +10 |
| Siege a neutral port | −10 |
| Bribe a patrol | −2 |
| Rob a trader NPC | **−10** (plus +5 × tier Syndicate, −25 Guild standing) |
| Caught in a customs scan | −5 |
| Contraband sale detected | −25 |
| Jettison mining workers | −10 per worker |
| Siege a Federation-aligned port | −25 |
| Daily missions | ±5 to ±15 |
| Faction missions | ±25 daily, ±30 elite arc |

Mission alignment rewards are capped at **±30** by validation.

---

## Smuggling

| Contraband | Rides on | Fence buy | Max/txn | Sell × | Risk |
|---|---|---|---|---|---|
| Illicit Organics | organics | market-priced | 100 | ×2.0 | low |
| Stolen Equipment | equipment | market-priced | 100 | ×2.0 | medium |
| Black Tech | equipment | market-priced | 100 | ×3.5 | high |

| Region | Premium | Sale detection |
|---|---|---|
| `fed_core` | ×1.50 | 22% |
| `fed_space` | ×1.40 | 18% |
| `inner` | ×1.25 | 12% |
| `middle` | ×1.15 | 8% |
| `outer` | ×1.00 | 4% |
| `outer_rim` | ×1.00 | 1% |

Fence sale price: **×1.20** of the local sell price, no detection roll.
Fence buy prices follow the local market (since v2.3.0).

```
scan chance = 0.75 − 0.50 (goods cloak) − 0.30 (stealth plating)
                   − smuggler role (max 0.08)
floored at 0.05
```

| Knob | Default |
|---|---|
| Scan cooldown | 30 minutes |
| Seizure fine | 10% of cost basis, on the overflow above hidden holds only |
| Sale-detection fine | 50% of the sale, min 500 cr, capped at wallet |
| Bribe | 25% of street value, clamped 500–25,000 |
| Pirate-line hidden holds | 25% |
| Hidden compartments | +15% (T3), +25% (T4), +60% (epic) |

---

## Bounties

| Knob | Default |
|---|---|
| Player-posted bounty | 500 – 100,000 cr |
| Posting fee | +10% |
| Player bounty expiry | 7 days |
| Faction bounty | `min(500 × tierMult × sqrt(kills), 500,000)` |
| Tier multipliers | ×1, ×2, ×4, ×8, ×16 |
| Faction bounty expiry | never |

---

## Planets

| Knob | Default |
|---|---|
| Claim cost | 150,000 cr |
| Claim level gate | ~a fifth up the season ladder |
| Claim alignment gate | ±100 in aligned territory |
| Claim alignment reward | ±250 |
| Claim truce | 12 hours |
| Capture truce | 24 hours |
| Starting population | 50 |
| Base population cap | 500 (+250 / Habitat level) |
| Base storage cap | 2,000 (+2,000 / Warehouse level) |
| Base garrison cap | 500 (×2 per Citadel level) |
| Structure max level | 5 |
| Starbase | 1,500,000 cr, a past-midpoint ladder gate, all structures at 5 |
| Export rate | 30 cr per unit |
| Minelaying (Barracks 1+) | 6 garrison fighters + 150 cr per mine, max 20/order, 1 turn, level-gated |
| Trading post shelf price | anchor × 0.9, floored 2% above the best local port sell price |

### Structures

| Structure | Base | Multiplier | Ladder gate |
|---|---|---|---|
| Warehouse | 5,000 | ×1.8 | — |
| Habitat | 6,000 | ×1.8 | — |
| Factory | 7,500 | ×1.8 | early |
| Shield Generator | 10,000 | ×2.0 | early |
| Barracks | 7,500 | ×1.9 | ~a quarter up |
| Citadel | 25,000 | ×2.0 | ~a third up + Factory 3 & Shield 3 |

Level *n* costs `floor(base × multiplier^(n−1))`.

### Production per tick

```
output = floor(baseRate
              × (1 + 0.15 × factoryLevel)
              × (0.2 + 0.8 × population ÷ populationCap)
              × regionMultiplier
              × (1 + 0.10 × citadelLevel))

population growth = floor(10 × (1 + 0.10 × habitatLevel)) − floor(population × 1%)
```

Base rates: fuel 35, organics 25, equipment 13. Region multiplier 1.10 in
`outer`, 1.05 in `outer_rim`, 1.00 elsewhere. Barracks add 4 garrison
fighters per level per tick.

### Raids

```
attackerPower = (fighters × 0.8 × combatAI + shields × 1.2 + torpedoes × 2.0)
                × (1 + siegeBonus)
defenderPower = max(10, garrison × 0.8 × (1 + structureDefense) + structuralDefense)
structureDefense  = (1 + 0.15 × shieldLvl) × (1 + 0.10 × citadelLvl) − 1
structuralDefense = 12 × shieldLvl + 25 × citadelLvl
winChance = attackerPower ÷ (attackerPower + defenderPower) ± 0.02
```

| Outcome | Effect |
|---|---|
| Win | Garrison → 50%; loot 25% of each stored commodity (holds-capped) + 10% of wallet capped 5,000 cr; you lose `fighters × (1−winProb) × 30%` and `shields × (1−winProb) × 20%` |
| Loss | Garrison → 80%; **all** fighters lost; `max(shields, 75% of shields + hull)` damage |

Capture requires the garrison at **zero**.

---

## Port capture

| Knob | Default |
|---|---|
| Siege cost | 3 turns, behind the mid-ladder siege gate |
| Attack cooldown | 1 hour |
| Post-capture truce | 24 hours |
| Corp hold cap | `max(1, members ÷ 3)` |
| Garrison seed | `stockValue ÷ 100,000`, clamped 30–200 |
| Garrison regrowth | 10% of seed per tick |
| Tax skim to the corp | 50% (the rest burns) |
| Member tax factor | ×0.5 |
| Occupation levy | +1pp |
| Upkeep per tick | `max(500, stockValue × 0.25%)` |
| Delinquency | reverts after 2 unpaid ticks |
| Win skim | 0.1% of stock value, capped 2,000 |
| Raze loot | 10% of stock value, capped 25,000 |

Never capturable: Stardock, Federation Ports, Pirate Haven, Merchant Exchange.

---

## Progression

```
level = floor(sqrt(XP ÷ divisor)) + 1        capped at the season's maxLevel
XP for level n = (n − 1)² × divisor
```

**The curve is pinned per season.** Pre-migration seasons run a 50-level
ladder; every new season runs a 100-level ladder whose divisor is tuned to
the season's length, so each gate lands at the same fraction of the season
regardless of pace. Catalog XP gates (ship tiers, drives) are re-derived on
the season's own curve, so level and XP requirements always agree.

Curve validation target: 4,500 XP/day over 12 weeks on the reference ladder.

### Level gates, in ladder order

| Depth (fraction of the ladder) | Unlocks |
|---|---|
| first rungs | bounty_post, blackmarket_buy |
| early (~8%) | ship tier 2, factory, shield, corp_create |
| ~14% | contraband_sell |
| ~18% | planet_claim, fleet_join |
| ~22% | ship tier 3, barracks |
| ~28% | port_siege, fleet_lead |
| ~34% | citadel |
| ~43% | ship tier 4 |
| ~51% | starbase_build |
| ~70% | ship tier 5 |
| ~80% | tesseract |

The in-game unlock list shows your season's exact levels. Gates fail open:
anything not listed is available at level 1.

### Exploration XP

10 base, +25 port, +50 planet, +100 landmark, × the galaxy XP multiplier.

### Roles

| Role | Stat | T1–T5 | Perk per tier | Cap |
|---|---|---|---|---|
| Trader | tradesCompleted | 15 / 40 / 90 / 175 / 300 | −0.4pp tax | −2pp |
| Smuggler | contrabandSold | 25 / 75 / 180 / 350 / 600 | −2pp scan | −8pp |
| Fighter | kills | 4 / 12 / 30 / 60 / 110 | +1% combat | +5% |
| Explorer | sectorsExplored | 20 / 60 / 140 / 280 / 500 | −1/−1/−2/−2/−3 warp turns | −3 |

### Streaks

| Day | Credits | XP | Turns |
|---|---|---|---|
| 3 | 1,000 | 50 | — |
| 7 | 5,000 | 200 | 5 |
| 14 | 10,000 | 500 | 10 |
| 30 | 25,000 | 1,000 | 20 |

Grace: one missed day forgiven per streak.

### Prestige tiers

| Titles held | Tier |
|---|---|
| 0 / 1 / 3 / 6 / 9 / 12 / 15 | Drifter / Spacer / Voyager / Veteran / Ace / Legend / Mythic |

Level ranks: Recruit 1, Cadet 3, Pilot 6, Ensign 10, Lieutenant 15,
Commander 21, Captain 28, Fleet Commander 36, Admiral 45.

---

## NPCs

| Type | Base rate/move | Blocked in | Max/sector | Loot |
|---|---|---|---|---|
| Pirate | 3.0% | Federation territory | 3 | 500–2,000 cr |
| Trader | 2.0% | — | 2 | 100–500 cr |
| Patrol | 1.5% | Pirate territory | 2 | none |

| Region | Pirate | Trader | Patrol |
|---|---|---|---|
| `fed_core` | 0 | 0 | ×4.0 |
| `fed_space` | 0 | ×0.5 | ×2.5 |
| `inner` | ×0.5 | ×1.0 | ×1.5 |
| `middle` | ×1.0 | ×1.2 | ×1.0 |
| `outer` | ×1.5 | ×0.8 | ×0.5 |
| `outer_rim` | ×2.0 | ×0.5 | 0 |

Loot tier multipliers ×0.75 / ×1.00 / ×1.25 / ×1.50 / ×1.75.

| Knob | Default |
|---|---|
| Transient despawn | 2 hours |
| Wander chance per tick | 20% |
| Named-NPC damage persistence | on |
| Named-NPC regeneration | 25% of spawn strength per tick |
| Rumor frequency | 75% (Saber Quill 25%) |
| Rumor location fuzz | within 2 hops |
| Pending encounter TTL | 10 minutes |
| Warp interruption journey cap | 30% total |
| Aggression threshold | ±300 |

### Encounter options

| Option | Effect |
|---|---|
| Surrender to a pirate | 30% of cargo units; empty holds ⇒ 10% of wallet capped 5,000 |
| Jettison | 25% of cargo, guaranteed escape |
| Jettison contraband | all contraband |
| Bribe a pirate | 500 / 1,500 / 4,000 / 10,000 / 25,000 by tier; 65% base, +15pp if pirate-aligned |
| Bribe a patrol | 60%, 2,000 cr fine on failure |
| Rob a trader | yield-or-resist — see the trader-interactions table above |
| Trade with a trader | anchor ×1.35 buy / ×0.65 sell, 3 deals — see above |

Pirate ambush chance: 100% against Federation-aligned in pirate territory,
66% elsewhere; 66% / 33% against neutrals; never against pirate-aligned.

---

## The world

| Knob | Default |
|---|---|
| Sectors | 500 (range 20 – 65,536) |
| Port density | 15% |
| Planet density | 10% |
| Hazard density | 6% |
| Landmarks | 3, each with a shared 50,000 cr budget, 24h per-player cooldown |
| Named NPCs | 12 (5 pirate, 5 Federation, 2 merchant princes) |
| Pirate band | outermost 8% of sectors, contiguous |
| Diagonal link fraction | 20%, of which 10% are one-way |
| Federation highways | `max(2, sectors ÷ 500)` |
| One-way smuggling routes | `max(2, sectors ÷ 1,000)` |
| Wormholes | 2 core–rim bridges + 3 random, 30% unstable |
| Unstable scatter chance | 20% |

Region bands by distance from Sector 0 as a fraction of map radius:
`fed_core` <0.08 · `fed_space` <0.20 · `inner` <0.40 · `middle` <0.65 ·
`outer` <0.85 · `outer_rim` beyond.

---

## Corporations

| Knob | Default |
|---|---|
| Founding cost | 50,000 cr (wallet, then bank) |
| Level gate | early ladder |
| Member cap | `max(10, seasonPlayerCap ÷ 5)` |
| Name length | 3–50 |
| Bank transaction bounds | 1 – 10,000,000 |
| Fleet cap | 3 ships |
| Fleet form / join | mid-ladder gate to lead / an earlier gate to join |
| Chat message limit | 500 characters |
| Chat cooldown | 3s per player, 30/min per corp |
| Chat retention | 500 messages or 14 days, whichever is longer |

Policy defaults: `storage.view` on, `storage.deposit` on,
`storage.withdraw` **off**, `defenses.view` on, `defenses.place` on,
`defenses.clear` **off**, `planet.build` **off**, `bank.spend` **off**.

---

## Social

| Knob | Default |
|---|---|
| Player announcement fee | 1,000 cr (pure sink; wallet then bank) |
| Announcements per cycle | 1 |
| Announcement length | 3–280 characters, profanity-gated, level-gated |
| Captain rename cooldown | 24 hours |
| Rename feed story | public, on |
