---
title: "Upgrades, Drives & Tech"
date: 2026-08-04
draft: false
description: "The upgrade ladder, warp and StarNav, and the ten tech modules"
weight: 8
toc: true
---

*Accurate as of v2.0.8 (August 2026).*

Three separate systems live behind the "upgrade" button, and they behave
differently.

- **Stat upgrades** are five-tier ladders on holds, shields, fighters and
  torpedoes. Bound to the ship.
- **Drives** are warp, StarNav and Tesseract. Bound to the ship.
- **Tech modules** are one-per-ship permanent installs. Bound to the ship.

All three die with the ship. There is no salvage.

## Stat upgrades

Each of the four stats has a five-tier ladder. The **total** you can add is a
fixed fraction of the hull's base stat:

| Archetype | Holds | Shields | Fighters | Torpedoes |
|---|---|---|---|---|
| Trading / Smuggling / Patrol | +100% | +50% | +100% | +100% |
| War / Raider / Enforcer | +50% | +50% | +200% | +200% |
| Balanced / Corsair / Dreadnought | +80% | +50% | +160% | +160% |

Notice the shape: **shields cap at +50% on everything**. The archetypes
differ on holds and on weapons, never on shields.

### How the ladder is priced

Holds distribute the total gain **30 / 20 / 20 / 15 / 15%** across five
tiers, at cost multipliers **×8 / 16 / 40 / 100 / 300** of the hull's hold
base cost.

Combat stats reach cumulative **25 / 45 / 60 / 70 / 80%** of the shape at
multipliers **×8 / 16 / 28 / 44 / 64**.

Two consequences worth internalizing:

1. **Early tiers are absurdly cheap relative to late ones.** Tier 1 holds on
   a hull with a 50 cr hold base costs 400 cr for 30% of the total gain. Tier
   5 costs 15,000 for 15%.
2. **Buying tier 1 and 2 on everything beats maxing anything.** The first two
   hold tiers give you half the total gain for 24 of the 464 total multiplier
   units. Spread wide before you go deep.

### What to buy first

Holds, if you're trading. It is the only upgrade that compounds — every extra
hold multiplies the return on every run you make for the rest of the season.

Shields, if you're fighting. Shields defend at weight 3.0, the highest
defensive weight in the game, and they are the layer that regenerates for
free every four hours.

Torpedoes are the strongest attack stat (weight 5.0) but they are *consumed*
in every fight — 20% base plus up to 50% more — and they cost 150 cr each to
replace. Fighters attack at 2.0, defend at 1.0, and cost 75.

## Drives

### Warp Drive

| | |
|---|---|
| Install | 15,000 cr |
| Requires | Tier-2+ hull, 100 XP |
| Upgrade | 15,000 cr × the new level |
| Max level | 5 |

Cost of a jump is `max(1, ceil(hops ÷ level))`. At level 5, a 20-hop journey
costs 4 turns.

Warp only reaches **sectors you have already visited**. See
[Navigation](/guide/navigation/#warp-drive) for interruption rules.

### StarNav 2002

| | |
|---|---|
| Install | 100,000 cr, requires 5,000 XP |
| Upgrade | 100,000 cr × the new level (L2 = 200k, L5 = 500k) |
| XP gates | 5,000 / 10,000 / 25,000 / 50,000 / 100,000 |
| Max level | 5 |

The passive scanner. It costs nothing to use and it never stops working. See
[Scanners & Intel](/guide/scanners-intel/) for what each level actually
resolves.

The single most important threshold: **StarNav 4 sees through ship cloaks.**

### Tesseract Drive

| | |
|---|---|
| Install | 10,000,000 cr |
| Requires | Tier-5 hull |
| Jump cost | Flat 25 turns, any distance, any visited sector |

> **Known problem.** The shipped catalog also gates it at *player level 100*,
> but the progression curve caps levels at **50**. As configured, nobody can
> install a Tesseract. Treat it as unavailable until a season fixes the gate.

## Tech modules

One of each per ship, permanent, wallet-only. Bought at ports running the
`upgrade` or `research` service — Tech Ports, Research Ports, the Pirate
Haven and the Merchant Exchange.

Every module's effect is computed **live from the flag**, not snapshotted into
your stats when you buy it. Changing hulls never leaves a stale bonus behind.

| Module | Cost | Level | Effect |
|---|---|---|---|
| Cargo Compressors | 8,000 | 5 | +20% holds, of the hull's **base** holds |
| Shield Booster | 10,000 | 6 | +15% max shields, of **base** shields |
| Attack Systems | 12,000 | 8 | +10% attack power |
| Armor Plating | 12,000 | 8 | +10% defense power |
| Combat AI | 15,000 | 10 | +20% fighter effectiveness, in combat **and** sieges |
| Advanced Sensors | 15,000 | 12 | Cuts a stealth attacker's first strike from +12pp to +6pp |
| Warp Optimizer | 18,000 | 12 | Warp jumps cost 1 fewer turn (never the Tesseract) |
| Stealth Plating | 15,000 | 15 | **−30pp** on customs scans, **+15pp** escape chance, +12pp first strike when attacking |
| **Patrol Transponder** | 20,000 | 15 | Federation only — patrols never materialize |
| **False Manifest** | 20,000 | 15 | Pirate only — one failed customs scan per day quietly rerolls |

The last two are faction-exclusive and require ±500 alignment on the matching
side.

### The ones that punch above their cost

**Stealth Plating** is the best 15,000 cr in the game if you fly anywhere
interesting. It is simultaneously the second-biggest customs counter, a
+15pp escape chance, and a first-strike bonus when you attack.

**Combat AI** at +20% fighter effectiveness applies in ship combat *and* in
port and planet sieges. If you siege anything, buy it.

**Cargo Compressors** at +20% of base holds stacks additively with the
trading line's signature ability. A Star Galleon (320 base holds, +10%
signature) with compressors runs 320 + 32 + 64 = 416 effective holds before a
single upgrade tier.

**Ion storms degrade every tech bonus by 20%** while you're fighting in one.
Attack Systems, Armor Plating and Combat AI all get shaved. Nebulas hit
fighters directly for −15%; radiation zones cut shield defense by 10%.
