---
title: "Navigation & Travel"
date: 2026-08-04
description: "Moving, warp, the Tesseract, wormholes, hazards and beacons"
weight: 30
group: fly
tags: [navigation]
changed_in: [2.3.0]
stats:
  - { label: "Move", value: "1 turn", sub: "per linked sector" }
  - { label: "Warp L5", value: "4 turns", sub: "for a 20-hop trip" }
  - { label: "Tesseract", value: "25 turns", sub: "to any visited sector" }
---

## Moving

Sectors are connected by links. Most links are bidirectional grid adjacency;
about one sector in five also carries a diagonal link, and a fraction of those
diagonals are **one-way**. A galaxy also gets a handful of long-range
**Federation highways** connecting the core to distant regions, and a handful
of **one-way smuggling routes** running out of pirate and rim space toward
distant sectors.

A move to a linked sector costs **1 turn** and runs the full arrival stack:

1. **Sector hazards** roll.
2. **Mines** in the sector roll.
3. **Limpet trackers** waiting in the sector latch onto you, silently.
4. An **NPC encounter** may roll.
5. If a patrol turns up, a **customs scan** may follow.

Arriving in a sector for the first time pays exploration XP: 10 base, +25 if
it has a port, +50 for a planet, +100 for a landmark.

Moving **breaks a ship cloak**.

## Warp drive

The Warp Drive turns hops into jumps.

- **Install:** 15,000 cr, requires a **tier-2+ hull** and a few levels on
  the season ladder — an early gate you'll clear in your first sessions.
- **Upgrade:** 15,000 cr × the new level, to **level 5**.
- **Cost:** `max(1, ceil(hops ÷ warpLevel))` turns.

At level 1 warp saves you nothing but the clicking. At level 5, a 20-hop
journey costs 4 turns instead of 20.

Three hard rules:

- **You can only warp to a sector you have already visited.** The route
  finder refuses unvisited destinations outright. Buy intel or fly there once.
- **A route has to exist.** One-way links mean the way back is not always the
  way you came.
- **The Warp Optimizer module** removes 1 turn, and the **Explorer role**
  removes 1 to 3 more. Both floor the total at 1.

### Interruption

A warp charges its **full cost up front** (since v2.3.0). If an NPC
interrupts you mid-flight, the journey truncates where you were stopped and
**the turns for the hops you didn't fly come back**.

The per-hop interruption chance is bounded so that **no journey exceeds a 30%
total chance** of being stopped, no matter how long it is. Players under PvP
immunity skip the roll entirely.

Warping through a hazard sector rolls that hazard at **25%** of the normal
chance. Arriving at a hazard destination rolls the full chance.

Warping breaks a cloak and clears landed status.

Sectors you pass through on a warp count as **explored** for missions and
goals (since v2.3.0). Exploration objectives no longer demand that you fly
every hop by hand.

## The Tesseract

An instant jump to any visited sector, any distance, for a flat **25 turns**.

- **Install:** 10,000,000 cr, tier-5 hull, and a level gate sitting at the
  very top of the season's ladder.
- No hop discovery, no interruption roll, no hazard pass-through.
- **Exempt from every turn discount in the game.**

> **The last unlock in the game.** The Tesseract is gated deeper in the
> ladder than anything else — deliberately. Whether a given season's ladder
> actually reaches it depends on that season's tuning: some running seasons
> cap out below the gate, in which case nobody installs one there, ever.
> Check the in-game unlock list for your season's numbers before you plan
> around it.

## Wormholes

Each galaxy generates a couple of core–rim bridges plus a few random
wormholes. Roughly 30% of them are **unstable**.

- Transit costs **1 turn** and you must be in the wormhole's origin sector.
- Some are bidirectional; some are not.
- **A stable transit bypasses mines and hazards entirely.** Wormholes are the
  one clean way through a mined sector.
- An **unstable** wormhole has a **20%** chance of scattering you to a random
  sector instead of its exit. A scattered arrival is a forced jump and it
  *does* roll arrival hazards.
- Limpets latch either way.

## Hazards

Hazards are sector properties, not events. About 6% of sectors carry one.

| Hazard | Chance on arrival | Effect |
|---|---|---|
| Asteroid field | 20% | 10–20 shield damage; in a fight, +10pp escape and −10% torpedo penetration |
| Radiation zone | 100% | 25 shield damage; in a fight, −10% shield defense |
| Minefield | 40% | 40–60 damage |
| Ion storm | 100% | No damage; in a fight, −20% to every tech module bonus |
| Nebula | 100% | No damage; in a fight, −15% fighter effectiveness |

Hazard damage lands on shields first and spills to hull at ×1.5 like all
damage. A hazard *can* kill you if your shields are down and your hull is
thin.

Arrivals by move, warp destination and tesseract destination all roll the
full chance. Warp pass-through rolls at 25%. Wormhole transit is exempt.

## Scanning

Two different things share the word "scan".

**Active scan** costs turns and reveals a radius around you: 1 turn per ring,
radius 1 to 3. It reports sectors and hazards, and — at StarNav 2 or better —
deployed ordnance by kind and quantity, though never who owns it.

**The StarNav passive sweep** is free and always available if you have the
drive. See [Scanners & Intel](/guide/scanners-intel/).

## Beacons

A **Navigation Beacon** is a public message you leave in a sector. Buy them at
any supply shop for 2,500 cr, deploy one for 0 turns, up to 140 characters,
**one beacon per player per sector**. Everyone who passes through sees your
handle on it — and the glyph of any beacon-mark insignia you hold. You can
remove your own at any time.

Private **sector notes** (280 characters) and a favorite flag cost nothing and
are yours alone.

## Landmarks

Three unique named landmarks generate per galaxy, always out past the inner
ring: The Silent Armada, Precursor Ruins, The Crystal Garden, The Cinder, The
Wanderer's Monolith.

Interacting costs **0 turns** but carries a **24-hour per-player cooldown**
for each landmark. Each landmark has a **shared loot budget of 50,000 cr**
that depletes across the whole galaxy — when it's gone, it's gone, and
whoever got there first got it. Jump-gate landmark exits roll arrival hazards.

Landmarks are worth **100 exploration XP** on first arrival, the richest
first-visit bonus in the game.

## Naming a sector

Sector names are a flex, not a mechanic. Naming one requires an unspent
**Cartographer's Mark** insignia, which is granted by the GM events desk and
consumed on use.

You must have visited the sector and be standing in it. Names are 3–24
characters, letters, numbers, spaces, apostrophes and hyphens, run through a
profanity gate, and one per sector forever. Operators can revoke a name.
