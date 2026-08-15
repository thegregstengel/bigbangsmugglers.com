---
title: "Ordnance, Limpets & Beacons"
date: 2026-08-04
draft: false
description: "Mines, drones, turrets, trackers, and the things you leave behind"
weight: 11
toc: true
---

*Accurate as of v2.0.8 (August 2026).*

Everything in this section follows the same model: **buy it as an item, carry
it, consume it at deploy**. Deploying charges no credits — the purchase was
the price.

Deployables are bought at the `supplies` service: the three starports and
Agricultural Ports.

## The catalog

| Item | Price | Max per purchase | Sector cap | Your cap |
|---|---|---|---|---|
| Proximity Mine | 250 | 50 | 100 | 50 |
| Sentry Drone | 1,500 | 20 | 50 | 20 |
| Turret | 3,000 | 8 | 20 | 8 |
| Sensor Buoy | 800 | 5 | 10 | 5 |
| Cloak Field | 5,000 | 2 | 1 | 2 |
| Limpet Tracker | 4,000 | 10 | — | 10 live |
| Navigation Beacon | 2,500 | 5 | — | one per sector |

Deploying costs **1 turn** for ordnance. Limpets and beacons cost **0**.

## No-deploy zones

Nothing may be deployed in `fed_core` or `fed_space`. The Federation does not
tolerate munitions in its own space, and the block is absolute.

## Mines — the only thing that fires on entry

**Mines are the only deployable that attacks automatically.** Everything else
is passive presence.

When a ship enters a sector with hostile mines:

- each mine rolls a **60%** chance to fire
- at most **3** detonate per entry
- each detonation deals `attack × 4–6` damage — with attack 8, that's 32–48
  per mine, up to about 144 for a full triple

Damage runs through the standard shields-then-hull-at-×1.5 pipeline. **Mines
can kill you outright.**

What mines do *not* spare:

- **They do not spare your corp-mates.** Deployables have never checked corp
  membership. If you mine a lane your corporation uses, you will hit your own
  people.

What they do spare:

- **PvP-immune ships.** Immunity covers deployables.
- **Anyone arriving by stable wormhole transit.** A stable wormhole bypasses
  mines and hazards entirely. A *scattered* unstable exit does not.

Mines decay at **2% per day**, compounding.

## Passive stacks

Sentry drones, turrets, sensor buoys and cloak fields sit in a sector and do
nothing on their own. They are area presence: visible on a scan, contributing
attack and defense values to any deliberate assault on the stack, and
killable.

| Item | Attack | Defense | Lifetime |
|---|---|---|---|
| Sentry Drone | 5 | 3 | decays 3%/day |
| Turret | 12 | 2 | decays 3%/day |
| Sensor Buoy | 0 | 1 | decays 1%/day |
| Cloak Field | 0 | 0 | **expires in 48 hours** |

Deployable **sector fighters no longer exist**. Fighters belong to planet
garrisons. Sectors get mines.

## Attacking ordnance

You can deliberately assault a stack in your sector for **1 turn**:

```
winChance = playerPower / (playerPower + ordnancePower) ± 20%
clamped to [5%, 95%]
```

Losing hurts. A defeat applies the **75% defeat loss rate** — you lose 75% of
your fighters and take 75% of your defense pool as damage, through the hull
spill. **Attacking a heavy stack can destroy your ship.**

## Seeing deployables

Active scans and StarNav sweeps report deployables only at **StarNav 2 or
better**. Below that you see sectors and hazards and nothing else.

What a scan reports is **kind and quantity**. It never reports ownership. You
can see that a sector holds 40 mines. You cannot see whose they are until
they detonate.

## Limpet trackers

A limpet is a hull tag, not a weapon.

Plant one in a sector for **0 turns**. It waits. The **first non-owner player
ship** to arrive gets it attached **silently** — no notification, no warning.
From then on, **every move that ship makes updates the limpet's last-known
sector for you**.

- A **cloak fools sensors, not a device bolted to your hull.** Limpets keep
  reporting through a cloak. A cloaked ship arriving in a sector cannot be
  *newly* latched, but an existing limpet keeps working.
- **PvP-immune ships cannot be latched.**
- **Corp membership is not checked.** You will tag your own people.
- Cap: **10 live limpets** per player per galaxy, planted and attached
  combined.
- A **planted** limpet waits indefinitely. An **attached** one reports for
  **48 hours** and then falls off.
- You can self-destruct your own at any time. No refund.

### Getting them off

A **shipyard limpet sweep** costs a flat **10,000 cr** and is charged **even
if you're clean**. It scrubs every attached tracker and reveals **each
planter's handle and the sector they planted in**.

If you think you're being followed, the sweep is how you find out who. If
you're wrong, it cost you 10,000 for the peace of mind.

### The Warrant

The epic hull **The Warrant** makes any limpet planted while flying it
**never expire** once attached. That's decided at latch time and never
revisited — switching hulls later doesn't retroactively expire an eternal
tracker, and switching *to* The Warrant doesn't extend older latches.

## Navigation beacons

A public message in a sector. 2,500 cr, 0 turns, up to 140 characters,
**one per player per sector**.

Everyone who passes through sees your handle on it, and the glyph of any
beacon-mark insignia you hold — the **Corsair Sigil** (☠) is a GM-event
exclusive that marks every beacon you plant.

Remove your own at any time.

Beacons are also the closest thing the game has to public communication
outside a corporation. There are no direct messages. If you want to leave
someone a note, you leave it in a sector.

## Private notes

Free, invisible to everyone else: a 280-character note per sector plus a
favorite flag. Cost nothing, take no turns, and are the correct place to
record which mining port was paying 260 for organics last cycle.
