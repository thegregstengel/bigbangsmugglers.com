---
title: "Combat"
date: 2026-07-02
draft: false
description: "Ship combat, PvP zones, combat resolution, loot, recovery, destruction, and fleet warfare"
weight: 7
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

Combat in Big Bang Smugglers is fast and automatic. When ships fight, the server makes a single roll: your attack power against the defender's defense power, adjusted by a handful of pre-roll effects. There are no manual inputs during the fight. Win and you loot the loser's credits. Lose and your ship is disabled — or destroyed outright if your defenses were already depleted when the fight began.

## PvP Zones

Player-vs-player combat is gated by **region**, not just territory:

| Region | PvP Status |
|--------|-----------|
| Federation Core | Never |
| Federation Space | Never |
| Inner Systems | No PvP |
| Middle Band | No PvP |
| Outer Reaches | PvP enabled (when galaxy PvP is on) |
| Outer Rim | PvP enabled (when galaxy PvP is on) |

Only the outer bands of the galaxy allow PvP — most neutral space has none, and Federation space is always safe regardless of galaxy settings. Galaxy PvP is on by default.

Even inside a PvP zone, several protections apply in both directions:

- **Docked ships** cannot attack or be attacked. All ports are safe havens.
- **Ships parked on a planet** they (or their corporation) own cannot be attacked until the planet is captured.
- **Disabled ships** cannot be attacked at all — being disabled *is* your protection while you wait for repair.
- **Cloaked ships** cannot be targeted unless the attacker's scanner reveals them (see [Scanners & Intel](/guide/scanners-intel/)).
- **PvP-immune ships** (recently defeated, or holding a defense contract) can neither attack nor be attacked.

The Battle Station modal shows a sector badge: a shield icon means safe zone, a sword icon means PvP is live here.

## Initiating Combat

From the Nav tab, tap the **Battle Station** button (visible when other players are detected in your sector), pick your target, and tap **Attack**. The attacker spends **1 turn**; the defender spends nothing.

**Friendly-fire protection:** Corporation members cannot attack each other — the attack is blocked automatically. One important caveat: this protection covers direct attacks only. Corp-mates still trigger each other's mines, sector defenses, and limpet trackers (see [Deployables](/guide/deployables/)).

---

## How Combat Resolves

Attack and defense are computed with **separate formulas**. Shields contribute nothing to attack; fighters and torpedoes contribute nothing to defense.

```
attack  = (basePower × 0.5) + (fighters × 2.0) + (torpedoes × 5.0)
defense = (basePower × 0.5) + (shields × 3.0)
```

Both sides then apply their multipliers:

| Multiplier | Effect |
|------------|--------|
| Ship role | Each hull class carries an offense and defense multiplier |
| Tech upgrades | Advanced Attack Systems +10% offense; Reinforced Armor Plating +10% defense; Combat AI Core +20% effective fighters |
| Ship tier bonus | +4% per tier above 1, up to +16% at Tier 5 — this is the **ship's** tier, not your pilot level |
| Region bonus | See below |

**Region bonuses** key off the **ship hull's faction** (Federation, Pirate, or neutral hull class), not your personal alignment:

| Region | Bonus |
|--------|-------|
| Federation Core | +10% defense for Federation hulls |
| Federation Space | +5% defense for Federation hulls |
| Middle Band | +2% attack for any attacker |
| Outer Reaches | +5% attack for any attacker |
| Outer Rim | +10% for Pirate hulls (attacking or defending) |

The base win probability is `attack / (attack + defense)`, then four pre-roll effects adjust it:

- **Torpedo shield penetration:** each attacker torpedo bypasses 1% of the defender's shield defense contribution, capped at 50%.
- **Fighter skirmish:** fighter superiority shifts win odds by up to ±15%.
- **Stealth first strike:** an attacker with Stealth Hull Plating (or a stealth hull ability) gains +12% win probability; a defender with sensors negates 6 points of it.
- **Random factor:** each side's power is multiplied by a random 0.98–1.02.

The final win probability is always **clamped between 5% and 95%** — no fight is ever a sure thing, and none is truly hopeless.

### Win Odds Labels

| Label | Win Chance |
|-------|-----------|
| Heavily Favored | 75%+ |
| Favored | 60–74% |
| Even Odds | 45–59% |
| Risky | 30–44% |
| Dangerous | Below 30% |

The Battle Station modal shows no odds preview for PvP targets — only ship class and alignment — so scout before you swing. NPC engage modals do show a power comparison, but the preview math is approximate; the server's roll is what counts.

### Both Sides Take Losses

Combat is attritional. The **winner** loses a fraction of fighters, shields, and torpedoes scaled by how close the fight was — shields mitigate your own losses. The **loser** loses between 50% and 97.5% of each stat depending on how lopsided the defeat was, and is disabled (or destroyed — see below).

### Escaping (Defenders Only)

When you are *attacked*, your ship automatically attempts to escape before any shots are fired, based on its escape rating (clamped 5–85%; Stealth Hull Plating adds +15%). A successful escape ends combat with zero losses on both sides. Attackers never get an escape roll — once you initiate, you fight to the end.

---

## Loot

**PvP loot is credits only.** The winner steals a percentage of the loser's on-hand (wallet) credits, determined by the winner's hull faction:

| Winner's hull faction | Credits looted |
|-----------------------|---------------|
| Neutral | 25% |
| Federation | 20% |
| Pirate | 35% |

The steal is capped by the **winner's ship tier**:

| Winner's tier | Credit cap |
|---------------|-----------|
| 1 | 5,000 cr |
| 2 | 15,000 cr |
| 3 | 40,000 cr |
| 4 | 100,000 cr |
| 5 | 200,000 cr |

Two things combat can never take from you:

- **Banked credits.** Only wallet credits are lootable. Bank your profits before flying into PvP space.
- **Contraband.** Contraband cargo is never lootable in combat.

If the defender wins, the same credit-loot logic applies in reverse. NPC kills pay from loot tables instead — see [NPCs & Encounters](/guide/npcs/).

**Bounties:** if the attacker wins and the target carries active bounties, player-posted bounties pay out instantly; faction bounties create a claim you redeem at the issuing faction's registry. See [Bounties](/guide/bounties/).

### Alignment Effects

Combat shifts your alignment based on the target's **hull faction**: attacking Federation-hull players costs −8 on a win (−3 on a loss), Pirate-hull players pay +6/+2 toward Federation, neutral hulls −2/−1. Successfully defending against a pirate-hull attacker earns +2. See [Reputation & Factions](/guide/reputation-factions/) for the full ladder.

---

## Disable and Recovery

A disabled ship cannot move, attack, or be attacked. Recovery is automatic at the **next 4-hour turn-cycle boundary** (00/04/08/12/16/20 UTC): status returns to OK and shields are restored to 50% of max. Fighters and torpedoes are **not** restored — they are consumables you re-buy.

You also get **2 minutes of PvP immunity** immediately after losing a fight. That 2-minute window is an anti-spawn-camping shield, not a repair timer — the repair is the 4-hour boundary (or a paid repair, below).

## Two Repair Paths

You never have to wait for the boundary if you can pay:

| Path | Where | Restores | Cost | Turns |
|------|-------|----------|------|-------|
| **Port Repair** | Nav tab → port/repair-station card | Everything to max — shields, fighters, AND torpedoes; clears disabled status | 5 cr/shield + 10 cr/fighter + 15 cr/torpedo of damage, minimum 200 cr, scaled by reputation | 0 |
| **Field Repair Kit** | Ship tab → disabled banner | Shields to 50% only | Tier 1/2/3: 600 / 1,500 / 2,500 cr (Tier 4+: 2,500 + 2 × max shields) | 2 |
| **Shipyard Repair** | Starport → Shipyard | Shields to full only | Tier 1/2/3: 400 / 1,000 / 2,000 cr (Tier 4+: 2,500 + 1 × max shields) | 1 |

Port Repair is the only repair that replenishes fighters and torpedoes; the other two are shields-only. For field kit and shipyard repairs, if your wallet falls short the bank auto-draws the shortfall with a **10% fee**.

Fighters and torpedoes can also be restocked directly at any starport: **75 cr per fighter, 150 cr per torpedo**.

## Defense Contracts

Defense Stations (Nav tab) sell purchasable PvP immunity: **4,000 cr for 2 hours**, and contracts stack additively on any existing window. Immunity blocks incoming attacks, your own attacks, and — usefully — enemy mines and sector-defense fire.

---

## Ship Destruction and Escape Pods

A losing ship is normally disabled. It is **destroyed** instead when it entered the fight already stripped: **0 shields AND 0 fighters AND 0 torpedoes at combat start**, then lost. All three must be empty — a ship with even one fighter left survives as disabled.

### Depleted Defenses Warning

When your active ship hits 0/0/0, a warning banner appears on the Ship screen and Nav screen: one more lost fight destroys your ship. Repair or restock before engaging again.

### What Destruction Costs You

- The ship is gone permanently, along with **everything installed on it** — upgrades, warp drive, StarNav, Tesseract, cloak.
- All cargo aboard is lost.
- **All your remaining turns are wiped to 0.**
- Wallet, bank, and XP survive. Other ships in your Hangar are untouched.

### Escape Pod Respawn

Your pilot survives. The pod flies to the sector of a planet where you have a built Starbase; if you have none, you respawn at **Sector 0** (the Federation home sector). If you own another ship in the galaxy, it activates there automatically. If not, you receive a free starter vessel — the "SS Starter" (20 holds, 15 shields, 0 fighters, 0 torpedoes).

---

## Fleet Combat

Corporation members in the same sector can fight as a fleet.

- **Fleet size is capped at 3**, including the leader.
- Members must be in the same corporation, co-located in the sector, uncloaked, undocked, and not disabled. Docked corp-mates are not eligible.
- Form, join, and leave from the **Battle Station modal** in the Nav tab (Corp Fleet section). Forming and leaving are free; the leader leaving disbands the fleet.
- Only the **leader** initiates a fleet attack and pays the 1 turn — and the leader gets the kill credit. Every member shares the alignment change and earns reputation and XP.
- Resolution is **one combined roll**: the fleet fights as a single attacker with the full sum of all members' fighters, shields, and torpedoes on the leader's hull profile.
- **Credit loot goes to the corporation bank** — it is never split among members.
- Cargo from fleet victories requires a corporation Starbase for storage; **without a corp Starbase, cargo is forfeited outright**. See [Corporations & Fleets](/guide/corporations-fleets/).
- A fleet loss disables every member, and any member who entered at 0/0/0 is destroyed.

Fleet combat shows a result toast rather than the full recap screen.

---

## Warp Interruptions

Every warp hop can spawn an NPC encounter. **Any** NPC — pirate, patrol, or trader — halts the warp at that hop, and your unused hop turns are refunded pro-rata. Only an **auto-aggressive pirate forces combat**, resolved and committed server-side before you see it — there is no fleeing a warp ambush. Non-aggressive interruptions just strand you in that sector with the NPC.

Interruption risk is about 5% per hop on short warps, but the total chance over any single journey is **capped at roughly 30%** — long jumps are not proportionally more dangerous.

---

## Sector Defenses and Mines

Some sectors shoot back the moment you arrive — before you can act.

- **Sector defenses:** enemy garrison-backed defenses deployed to a sector **auto-engage on every entry** (move or warp), dealing up to **2,000 damage** — shields first, overflow chipping fighters. The standing garrison is not consumed by firing on you, so a defended sector hurts every single pass.
- **Mines:** up to 3 enemy mines trigger per pass, each dealing 30–50 shield damage. Triggered mines are consumed.

PvP immunity (including defense contracts) blocks both. Your own deployables never fire on you — but your corp-mates' will. Full mechanics, deployment, and counterplay: [Deployables](/guide/deployables/).

---

## Attacking Ports

Ports can be raided and even destroyed. This uses a separate, simpler siege formula, not the ship-combat math above.

**What you can attack:** depots, agricultural ports, tech ports, mining ports, research ports, pirate bases, and black markets — including pirate ports in pirate space. Starports and Federation hubs are never attackable.

**Cost:** 3 turns per attack, with a 1-hour cooldown per player. You must be in the port's sector and not disabled.

**Siege math:** your power = (fighters × 0.8) + (shields × 1.2) + (torpedoes × 2.0), against the port's garrison. (These are the old combat weights — they survive only in sieges.)

**Winning an attack** cuts the garrison by 50% and skims credits: the lesser of 0.1% of the port's stock value or 2,000 cr. Grind the garrison to zero and the port is **destroyed**, paying out the lesser of 10% of stock value or 25,000 cr. **Losing** disables your ship and wipes your fighters and shields, while the garrison only drops 20%.

**Every attempt has faction consequences**, win or lose:

| Target | Consequence |
|--------|-------------|
| Pirate base or black market | +10 alignment, −15 pirate reputation |
| Commerce port in Federation territory | −25 alignment, −15 Federation reputation, and a Federation bounty on you |
| Commerce port in neutral space | −10 alignment |

Destroyed ports don't leave a permanent hole: a replacement port of a random attackable type respawns elsewhere in the galaxy within about 4 hours.

---

## Upgrading for Combat

Tech upgrades that matter in a fight:

| Upgrade | Cost | XP required | Effect |
|---------|------|-------------|--------|
| Shield Booster Arrays | 10,000 cr | 1,500 | +15% shields (applied at purchase — buy while fully repaired for full value) |
| Combat AI Core | 15,000 cr | 3,000 | +20% fighter effectiveness |
| Advanced Attack Systems | 22,000 cr | 6,000 | +10% offense multiplier |
| Reinforced Armor Plating | 22,000 cr | 6,000 | +10% defense multiplier |

Restock fighters (75 cr) and torpedoes (150 cr) at any starport between fights — or let Port Repair restore everything in one bill. See [Tech Upgrades](/guide/tech-upgrades/).

---

## NPC Combat

NPC fights use the same resolution system described above, with one big difference in timing: **encounter outcomes are pre-rolled the moment the encounter fires**. An ambush is committed before you see the modal; tapping Attack on a non-aggressive NPC reveals a result that was already decided. Fleeing a non-aggressive encounter is always free. See [NPCs & Encounters](/guide/npcs/) for the interaction options and loot tables.

---

## Combat Recap and Feed

After every 1v1 fight (PvP or NPC), a recap screen shows both sides' stats, calculated power, your win probability, losses, loot, and any bounty collected. If you were disabled, it notes the next-reset repair timing. Fleet combat shows only a toast.

Three feed messages are created per combat: one private to the attacker with loot details, one private to the defender with losses, and one public showing who defeated whom. Popup alerts fire instantly for combat involving your ship.
