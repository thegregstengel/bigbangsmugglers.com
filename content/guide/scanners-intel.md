---
title: "Scanners, Cloaks & Intel"
date: 2026-08-04
draft: false
description: "StarNav tiers, active scans, cloaks, and paid intel"
weight: 12
toc: true
---

*Accurate as of v2.0.8 (August 2026).*

## StarNav 2002

The passive scanner. Once installed it runs continuously, costs nothing, and
takes no turns.

| | |
|---|---|
| Install | 100,000 cr, requires 5,000 XP |
| Upgrade | 100,000 cr × the new level — L2 200k, L3 300k, L4 400k, L5 500k |
| XP gates | 5,000 / 10,000 / 25,000 / 50,000 / 100,000 |
| Max level | 5 |

**Range** is `min(level, 3)` hops. Level 4 and 5 do not see further — they
see *better*.

**Detail** resolves per hop distance:

| Level | 1 hop | 2 hops | 3 hops |
|---|---|---|---|
| 1 | empty | — | — |
| 2 | empty | empty | — |
| 3 | **POI** | empty | empty |
| 4 | **full** | POI | empty |
| 5 | **full** | **full** | POI |

- **empty** — the sector exists and is linked; nothing else resolves.
- **POI** — points of interest: ports, planets, landmarks.
- **full** — everything the sector holds.

Sectors the device cannot fully resolve show as **unknown**, not as empty.
That distinction matters: an unknown sector is not a safe sector.

**Deployables** — mines, drones, turrets, buoys — are only reported at
**StarNav 2 or better**, by kind and quantity, never by owner.

## Active scans

A deliberate sweep of a radius around you, costing **1 turn per ring**,
radius 1 to 3. It reports sectors and hazards, plus deployables at StarNav 2+.

Use active scans when you're standing somewhere and need to know what's one
jump out. Use StarNav for the ambient picture.

## Cloaks

### Ship cloaking devices

Bought at any `blackmarket` service for **2,500 cr**, up to 5 at a time.
Activating one hides your ship for a **fixed 2 hours from activation**.

This used to run "until the next 4-hour world boundary", which meant
activating at 03:59 bought you sixty seconds. It's a fixed window now.

**A cloak breaks on action.** Trading, moving and warping all drop it. A
cloak is for sitting still somewhere dangerous, not for travelling
invisibly.

While cloaked:

- You cannot be attacked. A cloaked ship reads as **not present** to an
  attacker.
- Limpets waiting in a sector cannot newly latch onto you.
- **Limpets already attached keep reporting.** A cloak fools sensors, not a
  device bolted to your hull.

### Seeing through cloaks

**StarNav 4** is the threshold. At effective StarNav 4 or better, cloaked
ships are visible and attackable.

"Effective" because some hulls add to it for cloak detection only:

| Hull | Effect |
|---|---|
| Sector Warden (Federation patrol T3) | +1 — reveals from StarNav 3 |
| **Starlane Guardian** (Federation patrol T4) | **+2** — reveals from StarNav 2 |
| FSS Writ of the Council (epic) | +1 |
| **The Cartographer's Dream** (epic) | Sees through cloaks at **any** StarNav level |

Your actual StarNav data is untouched by these. They only move the cloak
threshold.

The Cartographer's Dream also reads the passive sweep **one level deeper**
than your installed drive — a level-4 drive resolves like a 5.

### Goods cloaking devices

A different item entirely, and not a ship cloak. A **Goods Cloaking Device**
(750 cr, blackmarket) reduces a customs scan chance by **50 percentage
points** — and is **consumed by the attempt whether or not it worked**.

See [Smuggling](/guide/smuggling/#counters).

## Cloak fields

A sector-level deployable, not a ship system. 5,000 cr, one per sector, two
per player, **expires after 48 hours**. It contributes no attack and no
defense; it is area concealment.

## Paid intel

Ports running the `tavern` or `research` service sell intel for **2,000 cr**.

It reveals the **five nearest unvisited sectors** and marks them visited.
That last part is the important bit: **warp only reaches visited sectors**,
so intel is how you extend your warp network without flying the hops.

It pays **no exploration XP** — you didn't go there. If the galaxy is fully
explored you get `NOTHING_TO_REVEAL` and pay nothing.

## The price board

The Merchant Exchange's exclusive service. Live prices and stock for **every
port in every sector you have visited**, nearest first, up to 200 ports. Free,
no turns.

It is the best intel in the game and it costs nothing but knowing where the
Exchange is.

## Advanced Sensors

The tech module (15,000 cr, level 12) is not a scanner. It is a combat
counter: it cuts a stealth attacker's first-strike bonus from +12 percentage
points of win probability down to +6.

The Federation patrol line's sensor-edge signature counts as Advanced Sensors
for this purpose, on top of its cloak-detection bonus.

## What nobody can see

- **Who owns a deployable.** Scans report kind and quantity only.
- **Exact player balances.** Leaderboards stopped exposing them in v2.0.8.
- **A limpet on your hull.** Attachment is silent. The only way to find out is
  a 10,000 cr shipyard sweep.
