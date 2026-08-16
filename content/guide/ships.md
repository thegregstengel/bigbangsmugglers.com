---
title: "Ships"
date: 2026-08-04
draft: false
description: "Three archetypes, three hull lines, five tiers, and the epics"
weight: 7
toc: true
---

*Accurate as of v2.0.18 (August 2026).*

## The shape of the catalog

**45 purchasable hulls**, plus the SS Starter you can't buy, plus **six epic
hulls you can only earn**.

The 45 are three **archetypes** × three **lines** × five **tiers**. Every one
of the 45 has a provably unique stat block — that is enforced by an automated
test, not a convention.

### The three archetypes

| Archetype | Holds | Combat | Hull multiplier |
|---|---|---|---|
| **Trading** | Deepest | Weakest | ×0.80 |
| **War** | Shallowest | Heaviest | ×1.25 |
| **Balanced** | Middle | Middle | ×1.00 |

### The three lines

| Line | Roles | Doctrine |
|---|---|---|
| **Neutral spine** | trading, war, balanced | The baseline. No faction, no lock, no bonus. Stocked everywhere. |
| **Federation** | patrol, enforcer, dreadnought | **+10% base shields** at every tier. |
| **Pirate** | smuggling, raider, corsair | **+0.10 escape** over the Federation mirror, plus hidden holds. |

Federation and Pirate hulls are mirror images: same holds, same fighters,
same torpedoes, same hull. The line decides what they do *better*.

**Federation = shields. Pirate = escape and hidden compartments. Neutral =
the baseline.**

## The tier ladder

| Tier | Cost | Level gate | Shields (neutral/pirate) | Shields (Federation) |
|---|---|---|---|---|
| 1 | 5,000 | none | 150 | **165** |
| 2 | 15,000 | early ladder | 225 | **250** |
| 3 | 40,000 | about a quarter up | 350 | **385** |
| 4 | 100,000 | near the middle | 525 | **580** |
| 5 | 250,000 | about two-thirds up | 800 | **880** |

The gate *levels* are per-season: every season pins its own ladder, and each
tier's gate lands at the same fraction of the ladder whatever its length.
The shipyard shows your season's exact level and XP numbers, and the two
always agree — they are derived from the same curve.

Stocking is unlimited. There is no finite allocation of hulls at a shipyard —
if the yard carries the line, it will sell you as many as you can pay for.

## The T3+ allegiance lock

**Tier 1 and 2 faction hulls sell to anyone** standing on the right shipyard
floor. Alignment does not matter.

**Tier 3, 4 and 5 faction hulls are alignment-locked at ±500** — full
membership in that faction. A Federation T3 needs alignment ≥ +500; a Pirate
T3 needs ≤ −500.

The **neutral spine never locks**. Every neutral hull, all five tiers, sells
to anyone with the credits and the level. That is the whole point of the
spine: if you don't want to pick a side, you are not locked out of the
endgame — you just don't get the +10% shields or the +0.10 escape.

Where the lines are stocked:

| Shipyard | Stocks |
|---|---|
| Stardock, Federation Ports | Federation line + neutral spine |
| Pirate Haven, Pirate Bases | Pirate line + neutral spine |
| **Merchant Exchange** | **Neutral spine only** |

## Base stats

By archetype, tier 1 → 5:

| Archetype | Holds | Fighters | Torpedoes | Hull |
|---|---|---|---|---|
| Trading / Smuggling / Patrol | 60, 90, 140, 210, 320 | 13, 20, 29, 42, 65 | 7, 10, 16, 23, 35 | 80, 120, 180, 272, 400 |
| War / Raider / Enforcer | 25, 35, 50, 75, 110 | 33, 49, 75, 114, 172 | 17, 26, 40, 61, 93 | 125, 187, 281, 425, 625 |
| Balanced / Corsair / Dreadnought | 40, 60, 90, 135, 200 | 23, 33, 49, 75, 114 | 12, 17, 26, 40, 61 | 100, 150, 225, 340, 500 |

Escape ratings:

| Line | Trading role | War role | Balanced role |
|---|---|---|---|
| Neutral | 0.30 | 0.40 (0.30 at T5) | 0.50 |
| Federation | 0.30 | 0.40 (0.30 at T5) | 0.50 |
| **Pirate** | **0.40** | **0.50** (0.40 at T5) | **0.60** |

## The hulls

### Neutral spine

| Tier | Trading | War | Balanced |
|---|---|---|---|
| 1 | Nebula Merchant | Patrol Corvette | Frontier Scout |
| 2 | Corestar Freighter | Strike Frigate | Pathfinder |
| 3 | Tristar Hauler | Battle Cruiser | Vanguard Ranger |
| 4 | Vanguard Trader | Enforcer Dreadnought | Horizon Cruiser |
| 5 | **Star Galleon** | **Titan Battleship** | **Odyssey** |

### Federation line

| Tier | Patrol | Enforcer | Dreadnought |
|---|---|---|---|
| 1 | Customs Cutter | Peacekeeper | Vanguard Lance |
| 2 | Border Sentry | Lawbringer | Stellar Bulwark |
| 3 | Sector Warden | Iron Justicar | Nova Paladin |
| 4 | Starlane Guardian | Star Marshal | Astral Citadel |
| 5 | **Federation Aegis** | **Federation Bastion** | **Federation Sovereign** |

### Pirate line

| Tier | Smuggling | Raider | Corsair |
|---|---|---|---|
| 1 | Shadow Runner | Cutthroat | Rogue Gambit |
| 2 | Black Market Hauler | Reaver | Freebooter |
| 3 | Plunder Barge | Warlord | Blackheart |
| 4 | Marauder's Fortune | Blood Talon | Crimson Eclipse |
| 5 | **Pirate Leviathan** | **Pirate Juggernaut** | **Pirate Dominion** |

## Signature abilities

Every line carries a signature from tier 3 upward: modest at T3, stronger at
T4, and a flagship ability at T5.

| Hull | Ability |
|---|---|
| Tristar Hauler | +5% effective holds |
| Vanguard Trader | +8% effective holds |
| **Star Galleon** | **+10% effective holds** |
| Battle Cruiser | +4% combat damage |
| Enforcer Dreadnought | +7% combat damage |
| **Titan Battleship** | **+10% combat damage** |
| Vanguard Ranger | +2% to everything |
| Horizon Cruiser | +3% to everything |
| **Odyssey** | **+5% to everything** |
| Sector Warden | Sensor edge: counters stealth, +1 effective StarNav for cloak detection |
| Starlane Guardian | Sensor edge, **+2** effective StarNav — reveals cloaks from StarNav 2 |
| **Federation Aegis** | **+15% cargo seized on a win** |
| Iron Justicar | +8% siege attack power |
| Star Marshal | +12% siege attack power |
| **Federation Bastion** | **+10% combat damage** |
| Nova Paladin | +4% defense |
| Astral Citadel | +7% defense |
| **Federation Sovereign** | **+5% to everything** |
| Plunder Barge | Hidden compartments: 15% of holds invisible to customs |
| Marauder's Fortune | Hidden compartments: **25%** of holds |
| **Pirate Leviathan** | **+15% cargo from raids** |
| Warlord | +10% loot from port and planet raids |
| Blood Talon | +15% loot from raids |
| **Pirate Juggernaut** | **+10% combat damage** |
| Blackheart | +5% retreat chance when attacked |
| Crimson Eclipse | +8% retreat chance |
| **Pirate Dominion** | **+5% to everything** |

Note where the sensor edge sits: the **Starlane Guardian's** +2 is strictly
better than the Sector Warden's +1, so a T4 patrol hull reveals cloaked ships
from StarNav 2 while the T3 needs StarNav 3.

## Epic hulls

Six hulls that are never sold, never stocked, and cost nothing — because the
only way to get one is to claim an **epic goal ladder**. One per player per
season, granted into your garage inactive. They burn with the season like
every other ship.

| Hull | Line | Signature | Earned by |
|---|---|---|---|
| **FSS Writ of the Council** | Federation patrol | Federation patrols wave you through entirely; sensors counter stealth, +1 StarNav for cloaks | Redeem 50 Federation bounty claims and hold 2,500 Federation standing |
| **The Crimson Covenant** | Pirate raider | +25% raid loot, +10 escape | Win 40 planet raids, capture 20 enemy ports, hold 2,500 Syndicate standing |
| **The Golden Ledger** | Neutral trading | **360 base holds** — the deepest in the game — and +20% on top | 4,000 trade legs and 3,000 Merchant Guild standing |
| **The Cartographer's Dream** | Neutral balanced | Sees through cloaks at **any** StarNav level; passive sweeps read +1 level deeper | Explore 80% of the galaxy |
| **The Phantom Manifest** | Pirate smuggling | Hidden compartments: **60%** of holds | Sell 7,500 contraband units with **zero** sale-time busts all season |
| **The Warrant** | Neutral balanced | Limpets you plant **never expire** once attached | Collect 100 bounty heads and 1,000,000 cr in bounty money |

These are calibrated at roughly one player per season, each. The standing
floors are the hard part: standing decays 1% a day, so holding 2,500 means
earning about 125 a day *every* day, not banking it once.

## The hangar

Ships you own but aren't flying sit in your garage. You can switch between
them at any shipyard — or at your own starbase, which is what makes a rim
starbase a real forward base.

- **Selling** a ship pays **64% of its purchase price**. You cannot sell your
  active ship, and you cannot sell your last ship.
- **Switching** hulls is free.
- **Cargo does not always come with you.** Buying a hull with fewer holds
  than your current load scales your cargo down proportionally and the
  overflow is **destroyed**. The purchase screen tells you how many units you
  will lose.
- Renaming a ship costs 1,000 cr; 3 to 30 characters.

## Repair is not restock

These are two different actions at two different counters, and conflating
them will get you killed.

**Repair** restores **shields and hull only**.

| | Rate |
|---|---|
| Shields | 5 cr/point |
| Hull | **8 cr/point** — the priciest rate in the game |
| Minimum charge | 200 cr |

Repair is available at any port with the `repair` service, costs 0 turns, and
is **the only action in the game besides founding a corporation that can draw
from your bank** when your wallet is short.

**Restock** buys back munitions.

| | Rate |
|---|---|
| Fighter | 75 cr |
| Torpedo | 150 cr |

Restock is a shipyard service, wallet-only, and clamped to your effective
maximums.

Repair used to top your fighters and torpedoes back up. **It doesn't
anymore.** Walking away from a repair bay with full shields and empty tubes
is the single most common way to lose the next fight.

Shields also regenerate on their own: at every 4-hour world tick, any ship
below **50% of maximum shields** is topped up to exactly 50%. Ships already
at or above 50% are untouched. **Hull never regenerates** — port repair is
the only way up.

## Destruction and escape pods

There is exactly one way a ship dies: **hull reaches 0**. That applies
identically to PvP, NPC combat, ambushes, fleet fights, mines, hazards,
ordnance-attack defeats and siege defeats.

When it happens:

1. Looting resolves **first** — the winner takes their cut.
2. Your ship row is deleted. **Everything installed goes with it**: upgrade
   tiers, drives, tech modules. **All cargo is destroyed.**
3. **Every remaining turn is wiped to zero.** Death costs you the day.
4. Your **wallet, bank, XP, alignment and inventory are untouched.**
5. Standard PvP immunity is stamped on you.
6. The pod places you.

### Where the pod puts you

**If you own a starbase planet and have at least one other ship in the
garage**, you get a choice: Sector 0, or your starbase's sector. Until you
choose, you have no active ship and ship-requiring actions fail with a
`POD_CHOICE_PENDING` marker. If the starbase has fallen by the time you
choose, the choice degrades to Sector 0.

**Otherwise** you are placed at Sector 0 immediately, your first garage ship
is activated, and if the garage is empty you are granted a free SS Starter.

That's the whole loop. There is no disabled state, no field repair kit, no
sector-by-sector pod crawl, and no auto-recovery timer. Those all died with
1.x.

### What this means for how you fly

Hull is the resource that actually matters. Shields come back free every four
hours; hull only comes back for 8 cr a point at a repair bay, and there are
no repair bays in the outer rim.

A ship at 40% hull deep in pirate country is one bad roll from losing every
upgrade you ever bought on it. Repair before you push out, not after.
