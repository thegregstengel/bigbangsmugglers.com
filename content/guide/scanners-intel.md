---
title: "Scanners & Intel"
date: 2026-07-02
draft: false
description: "StarNav 2002, sector scans, purchased intel, cloaking, and who can see your ship"
weight: 12
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

Information wins wars and funds trade runs. Big Bang Smugglers gives you several layers of intel — a passive scanner that maps nearby space for free, active scans that spend turns for detail, intel you can buy at stations and taverns, and a preview before every warp. The counter-tool is the Cloaking Device, which takes you off everyone's screens until you act.

## StarNav 2002 — The Passive Scanner

The StarNav 2002 is a five-level ship scanner that renders a live spatial map of nearby sectors on the Nav screen. Reading it is free — it costs no turns and no credits — and it refreshes automatically when you change sectors.

### Installing and Upgrading

Buy it at any starport's Shipyard. It is installed on the **ship**, not on you — switching hulls means buying it again (or claiming/keeping a hull that already has one; see [Ships](/guide/ships/)).

| Level | Cost | XP required |
|-------|------|-------------|
| 1 (install) | 100,000 cr | 5,000 |
| 2 | 200,000 cr | 10,000 |
| 3 | 300,000 cr | 25,000 |
| 4 | 400,000 cr | 50,000 |
| 5 | 500,000 cr | 100,000 |

Prices are adjusted by your reputation standing, like other starport purchases.

### What Each Level Sees

Range is measured in hops (warp connections) from your current sector. Detail comes in three tiers: **existence** (the sector's number, faction territory, and connections), **POI counts** (ports, planets, starports), and **full intel** (player count, NPC count, hostile-NPC count).

| Level | Range | What you get |
|-------|-------|--------------|
| 1 | 1 hop | Existence only |
| 2 | 2 hops | Existence only |
| 3 | 3 hops | POI counts at 1 hop; existence beyond |
| 4 | 3 hops | **Full intel at 1 hop**; POI counts at 2 hops — **and sees through cloaks** |
| 5 | 3 hops | Full intel to 2 hops; POI counts at 3 hops |

Level 4 is the counter-intelligence breakpoint: it is the first level that shows player counts, and it reveals cloaked ships everywhere (see [The Cloaking Device](#the-cloaking-device)).

### Reading the Map

The STARNAV 2002 card on the Nav screen draws 1-hop sectors as large tappable circles and farther sectors as small dots, with POI icons per your detail tier. Sectors just beyond your range appear as dashed "?" blips at the map edge. Tap a 1-hop sector for a detail sheet with a **Warp to Sector** shortcut (a normal move — it costs a turn).

When the neighborhood gets dense, an expand button opens a full-screen pinch-and-zoom map of the same data with a per-sector detail panel.

One caution: the map refreshes when you change sectors, not while you sit still — player and NPC counts go stale if you stay parked.

## Active Sector Scans

The passive map never shows hazards, landmarks, or region names. For those you run an **active scan**: **Ship tab → Bridge → Scanners card**, pick a radius, tap Scan Sector.

- **Radius 1, 2, or 3 — the scan costs that many turns.**
- **No StarNav required.** This works from any ship at any scanner level.
- Each sector in radius reports: region, port count, planet count, landmark count, player count, NPC count, and **hazards** — the only intel source for hazards, landmarks, and region names.

Cloaked ships do not appear in scan results unless your ship carries StarNav level 4+. Scanning does not break your own cloak.

## Deployables Scan

Mines and sector defenses never show up on sector scans. The **Scan Deployables** button (same Scanners card, 1 turn, current sector only) is the dedicated sweep — but it only detects **large concentrations**. A minefield below roughly half the sector's mine cap can slip past even then. See [Deployables](/guide/deployables/) for the full detection rules.

Practical advice: treat the hostile-deployables warning banner as your tripwire. When a scan comes back hot, reroute; when it comes back clean, stay alert anyway.

## Buying Intel

Two venues sell sector reports, and both scale their price with your reputation standing:

| Venue | Where | Price (base) | You get |
|-------|-------|--------------|---------|
| Sector Intelligence | Nav → Stations → Research Station | 300 cr | 3 random sector reports (ports, starports, wormholes, landmarks) |
| Buy Intel | Nav → Port → Tavern (pirate, stardock, and black-market ports) | 500 cr | 5 reports on sectors you have **never visited** |

The tavern deal has a hidden bonus that makes it the better buy for explorers: **tavern reports make those sectors warp-eligible**. Warping normally requires prior knowledge of the destination, which means having visited it — tavern intel is the only way to add unvisited sectors to your warp map. At 500 cr for 5 sectors, it is a cheap way to extend your reach. Tavern intel is paid from your wallet only; the research-station purchase can dip into your bank if your wallet is short.

## Pre-Warp Intel

Before you confirm a warp, the preview shows the route, hop count, turn cost, and the **deployed fighters waiting at your destination** (both the total and how many are yours) — so you don't warp blind into a defended sector.

Know its limits: the preview counts free-floating deployed fighters only. Planet-launched garrison fighters, turrets, and sentry drones — which also auto-engage arrivals — do not appear. A clean preview is not a guarantee. The preview also requires prior knowledge of the destination, which visiting or tavern intel provides.

## The Cloaking Device

The Ship Cloaking Device is a single-use consumable from the Black Market: **2,500 cr each, up to 5 per purchase**. (Don't confuse it with the 750 cr Goods Cloaking Device, which hides contraband from cargo scans — that's a smuggling tool, not a ship cloak.)

Activate it from **Ship → Bridge → Ship Cloak**. Activation is free and instant, consumes one device, and lasts **until the next 4-hour turn boundary** — the same clock that resets your turns. Activate right after a turn reset for the full 4 hours of cover; activate five minutes before one and you've wasted a device.

**While cloaked, you are hidden from:**

- The players-in-sector list on everyone's Nav screen
- Sector scans
- Attack targeting — attackers get the same "not in your sector" result as if you were truly gone

**The cloak breaks the moment you act.** Moving, warping, trading, fighting, or deploying anything drops it instantly. Scanning and buying intel do not.

**What it is not:**

- It is **not a combat buff** — it adds nothing to any fight.
- It is **not proof against StarNav level 4+** — those scanners see through it, and their owners can attack you.
- It does **not work with fleets** — you cannot form or join a fleet while cloaked.

Think of it as offline protection: pop one before you log off in dangerous space, timed just after a reset.

## Who Can See You

Your ship appears in a sector's presence list — and is attackable — only when **all** of the following are true:

- It is your **active** ship
- It is **not docked** at a port
- It is **not parked** on a planet
- It is **not cloaked** (or the viewer has StarNav 4+)

Docking, planet parking, and cloaking each take you off the board. That is the defensive playbook in one line: when you stop playing, be docked, parked, or cloaked — never floating in open space.
