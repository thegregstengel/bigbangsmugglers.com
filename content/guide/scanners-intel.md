---
title: "Scanners, Cloaks & Intel"
date: 2026-08-04
description: "The STARNAV chart, its layers, active scans, cloaks, and paid intel"
weight: 32
group: fly
tags: [navigation, upgrades]
changed_in: [3.0.0, 2.9.0, 2.3.0, 2.0.14, 2.0.8]
stats:
  - { label: "StarNav", value: "100k cr", sub: "per level, to L5" }
  - { label: "Layers", value: "7", sub: "each level lights one up" }
  - { label: "Cloak", value: "2 h", sub: "fixed window, 2,500 cr" }
---

## STARNAV 2002 — the chart

Since 3.0, STARNAV is a **chart**: a map of every sector you have ever seen,
drawn on the galaxy's real grid. It lives on the Nav tab and opens full screen
with the ⤢ button. You can move it anywhere on the Nav tab, but not hide it.

The chart **remembers**. A sector you swept, scanned, visited or bought intel
on stays drawn, with the date you last saw it. Old information fades so you can
tell "last seen this morning" from "last seen last week". Nothing on the chart
is ever live unless you are looking at it right now.

### What each level lights up

The device costs what it always did, and each level still has its own season
gate:

| | |
|---|---|
| Install | 100,000 cr |
| Upgrade | 100,000 cr × the new level — L2 200k, L3 300k, L4 400k, L5 500k |
| Max level | 5 |

Every level now switches on a **layer** you can see:

| Level | Range | Layer it adds |
|---|---|---|
| 0 | — | **Chart + Trail** — every sector you've visited, the links between them, your recent route, ★ and notes, beacons, your planets and your corp's |
| 1 | 1 hop | **Sweep ring** — the sectors around you, live |
| 2 | 2 hops | **Hazards** — hazard glyphs, and mines/drones/buoys by kind and count from your scans |
| 3 | 3 hops | **Ports & prices** — ports and planets nearby, and the last prices you saw at every port |
| 4 | 3 hops | **Contacts** — ships and NPCs one hop out, cloaked ships, and the ghost ring of sectors one hop past your range |
| 5 | 3 hops | **Traffic** — full detail two hops out, and when you last saw ships in each sector |

Range is `min(level, 3)` hops. Levels 4 and 5 don't see further; they see more.
The Shipyard shows the layer next to each level, so you know what you're buying.

Layer chips sit above the chart. Tap one to hide or show that layer. A 🔒 chip
tells you which level opens it.

### Who holds what

By default the chart colours sectors by **control**:

| Colour | Means |
|---|---|
| Grey | Unexplored — you've never been there or resolved it |
| Green | Explored |
| Blue | You or your corp hold something there: a planet, a port, or your own deployments |
| Red | An enemy held a planet or port there **when you last saw it** |

Red is what *you* saw, dated like everything else on the chart — it is never a
live feed of other captains' territory, and enemy mines and drones never make a
sector red (their owners stay secret). A sector that is both yours and an
enemy's shows as **contested**. Switch the chart to **Region** colouring with
one tap.

Sectors the device cannot fully resolve show as **unknown**, not as empty.
An unknown sector is not a safe sector.

### Tap a sector

Tapping any sector opens its card: what your chart knows about it, how old
that is, and what you can do from here, with the turn cost on each button:

- **Move** (next door) · **Warp** (visited and reachable) · **Plan route** (draws
  the route on the chart; sectors you've never visited show as `?`)
- **Peek** (next door, a radius-1 scan) · **Scan around me** (from your own
  sector; pick 1–3 rings and see them on the chart first)
- **★, tag and note** · **Beacon** · **Wormhole transit**
- **Buy the visit** on an unvisited sector, when you're docked where intel is
  sold — see below.

The chart's search box finds sectors by number, name, your note or your tag,
with quick filters for ★ only, has a port, has a planet, has a landmark, and
noted. The old Explored list, Favorites and Recent Sectors all live here now:
the ★ Favorites link on the Sector panel opens the chart filtered to your stars,
and the Trail layer is your recent route.

**Clear hostile ordnance** — mines or drones in your own sector can be attacked
from your sector's card.

## Active scans

A deliberate sweep of a radius around you, costing **1 turn per ring**,
radius 1 to 3. Start it from your own sector's card on the chart. It reports
sectors and hazards, plus deployables at StarNav 2+, and everything it finds
stays on your chart with the time you scanned it.

Use active scans when you need to know what's out there *now*. Use the chart
for everything you've already seen.

## Cloaks

### Ship cloaking devices

Bought at any `blackmarket` service for **2,500 cr**, up to 5 at a time.
Activating one hides your ship for a **fixed 2 hours from activation**.

This used to run "until the next 4-hour world boundary", which meant
activating at 03:59 bought you sixty seconds. It's a fixed window now.

**A cloak breaks on action.** Trading, moving and warping drop it, and
since v2.3.0 so do sieges, raids, Black Market deals, banking and buying a
ship. A cloak is for sitting still somewhere dangerous, not for acting
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

### Full-Hold Cloak

A timed **luxury**, not a ship cloak and not a Goods Cloaking Device. Bought
at any port with the `blackmarket` service for **25,000,000** credits (since
v2.9.0). For **24 hours** from purchase, your whole hold reads empty to
**Federation patrol customs scans**: the scan does not register at all (no
seizure, no Goods Cloak spent, no clean-scan alignment reward either). It is
**not consumed** per use; it expires when the window ends. One live cloak at
a time.

It does **not** affect contraband **sale** detection at ports. Premium /
street sales still roll the regional chance; only a **hidden compartments**
signature scales that rate down. Fence sales never roll. Full-Hold Cloak,
Goods Cloaks, Stealth Plating, the smuggler role, and pirate-line hold
hiding do not help on sales.

See [Smuggling](/guide/smuggling/#selling-two-completely-different-actions)
for the sale path, and [customs counters](/guide/smuggling/#counters) for
the patrol stack.

## Cloak fields

A sector-level deployable, not a ship system. 5,000 cr, one per sector, two
per player, **expires after 48 hours**. It contributes no attack and no
defense; it is area concealment.

## Paid intel

Ports running the `tavern` or `research` service sell intel for **2,000 cr**.
There are two ways to buy it:

- **Five nearest** — the Research Lab row in a port's services reveals the five
  nearest sectors you haven't visited.
- **Buy the visit** — tap any unvisited sector on the chart and buy exactly
  that one. Same price.

Either way the sectors are named, their ports, planets and landmarks are
revealed, and they are **marked visited**. That matters because **warp only
reaches visited sectors**: intel is how you extend your warp network without
flying the hops.

Intel pays **no exploration XP** — you didn't go there. A sector you've
already visited can't be bought again.

## The price board

The Merchant Exchange's exclusive service, and since 3.0 the **chart updater**:
**Refresh prices from the board** in the Exchange's services writes the live prices of **every port in every
sector you have visited** (nearest first, up to 200 ports) into your chart's
price layer and opens the chart with the Ports layer on. Free, no turns.

Your chart also remembers every price you see yourself — the quote sheet at a
port, a quote, and what you actually paid. The Ports & prices layer (StarNav 3)
draws them all, each with its age.

## Advanced Sensors

The tech module (15,000 cr) is not a scanner. It is a combat
counter: it cuts a stealth attacker's first-strike bonus from +12 percentage
points of win probability down to +6.

The Federation patrol line's sensor-edge signature counts as Advanced Sensors
for this purpose, on top of its cloak-detection bonus.

## What nobody can see

- **Who owns a deployable** — from a scan. Scans report kind and quantity
  only. Detonations are another matter: a mine that hits you names its
  owner in your report.
- **Exact player balances.** Leaderboards stopped exposing them in v2.0.8.
- **A limpet on your hull.** Attachment is silent. The only way to find out is
  a 10,000 cr shipyard sweep.
