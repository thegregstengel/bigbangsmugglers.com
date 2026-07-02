---
title: "Gameplay Basics"
date: 2026-07-02
draft: false
description: "Core mechanics and game systems"
weight: 2
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

Master the fundamentals of Big Bang Smugglers.

## Navigation

### The Galaxy Map

- **Sectors**: each sector is a distinct location in the galaxy, numbered outward from Sector 0 at the center
- **Links**: lines between sectors show traversable routes
- **Territories**: Federation (the core), Pirate (the rim), and Neutral space (everything between)
- **Current location**: highlighted on the Nav screen

### Moving Around

Tap a connected sector on the Nav screen to move there — **1 turn** per move. (The adjacent-sector list is titled "Warp to," but those are ordinary moves; real warp jumps are below.)

Entering a sector isn't always quiet. A move can trigger enemy **mines**, **sector defense fighters**, and **limpet trackers** (see [Deployables](/guide/deployables/)), environmental hazard damage in asteroid fields, radiation zones, and minefields, and **NPC encounters** (about a 5% chance per move). Your first visit to any sector awards exploration XP, with bonuses for ports, planets, and landmarks.

### What Costs Turns

| Action | Turns |
|--------|-------|
| Move to adjacent sector | 1 |
| Trade (each buy or sell) | 1 |
| Warp jump | distance ÷ warp level, rounded up (min 1) |
| Tesseract jump | 25 flat |
| Wormhole transit | 1 |
| Attack a player or NPC | 1 |
| Port attack | 3 |
| Sector scan | 1 per radius level |
| Explore Ancient Ruins | 2 |
| Black hole transit | 1 |

Banking, ship and upgrade purchases, mission accepts, and deploying equipment are all turn-free.

### Warp Travel

A **warp drive** jumps you directly to any sector you've **previously visited** (nav-beacon landmark reveals and purchased intel also make sectors warp-eligible — see [Scanners & Intel](/guide/scanners-intel/)).

- **Install**: 15,000 cr at a starport shipyard; requires a Tier 2+ ship and 100 XP
- **Cost per jump**: distance ÷ warp level, rounded up, minimum 1 turn. Higher warp levels (up to 5) cover more sectors per turn; each level upgrade costs (level + 1) × 15,000 cr
- The **Warp Drive Optimizer** tech upgrade takes 1 turn off every warp (minimum 1)

**Warp interruptions:** each hop can spawn an NPC that halts your warp in that sector, but the total interruption chance is capped at roughly **30% per journey** no matter the distance, and unused turns are refunded. Only **auto-aggressive pirates force combat** when they interrupt — patrols, traders, and calmer pirates just leave you stranded a few hops short.

### Tesseract Drive

The Tesseract Drive is the endgame travel option: **10,000,000 cr**, and you need a **Tier 5 hull** and **level 100** to install it.

- **Flat 25 turns** per jump, any distance
- Instant and **uninterruptible** — no encounters mid-jump
- Mines, sector defenses, and limpet trackers waiting at the destination still trigger
- Visited sectors only; the Warp Drive Optimizer does not reduce the 25

Install it at the starport **Shipyard**; activate it with the **Tesseract Drive toggle** in the Nav screen's warp panel (it switches on automatically if it's your only drive). It coexists with a regular warp drive, so you can carry both.

### Wormholes

Wormholes connect distant sectors for **1 turn** and bypass everything — no encounters, no mines, no sector defenses on arrival. They only appear in the sector view when you're standing at an endpoint. Most are stable and two-way, but **unstable wormholes can scatter you** to a random sector instead, and some are one-way with no return trip.

### Landmarks

- **Nav Beacons** — activate for free to reveal up to 8 neighboring sectors on your map; revealed sectors become warp-eligible without visiting
- **Ancient Ruins** — explore for 2 turns; loot roll ranges from nothing to a few thousand credits, XP finds, and rare 10,000–25,000 cr jackpots
- **Anomalies** — investigate for free; a random boon or bane: credits, XP, even **+3 turns** — or shield damage, lost fighters, or a forced jump to parts unknown
- **Black Holes** — transit for 1 turn; hurls your ship to a far-off sector you don't choose, with a 20% chance of shield damage on the way through

Each landmark has a per-player cooldown (beacons 1 hour, anomalies 6 hours, ruins and black holes 24 hours), so ruins and anomalies are farmable on rotation.

## Your Ship

### Ship Stats

- **Shields**: your defense in combat — repairable, never bought
- **Fighters**: escort craft; steady attack power (75 cr each to restock)
- **Torpedoes**: heavy ordnance; the hardest-hitting attack stat per unit (150 cr each)
- **Cargo holds**: how much you can carry

In combat, fighters and torpedoes drive your attack and shields drive your defense, on top of your hull's base power. See [Combat](/guide/combat/) for the exact formula.

### Ship Roles

Ships come in six roles across two faction lines — three archetypes, each with a Federation and Pirate version:

- **Trading / Smuggling**: maximum cargo, light weapons — escape 30% / 40%
- **War / Raider**: high fighters and torpedoes, minimal cargo — escape 40% / 50%
- **Balanced / Corsair**: middle cargo and weapons, **best escape** — 50% / 60%

Shields are identical across all roles at a given tier — no role has "the highest shields." Every Pirate hull has **+10 escape** over its Federation mirror at the same price and stats (the Tier 5 War-line flagships give 10 points back in exchange for their special abilities; other lines keep full escape). See [Ships](/guide/ships/) for the full 30-ship catalog.

### The Hangar

You can own any number of ships. Buying a new one keeps your old ship in the **Hangar** — there's no trade-in. Your cargo transfers automatically; if the new ship has fewer holds, the overflow is lost.

The Hangar is a **place at every starport** (switch or sell) and at a planet with a Starbase you or your corp own (switch only). Switching your active ship is free, but only works at those locations. Selling pays a flat **64% of the purchase price**, only at starports — you can't sell your active ship or your last ship, and any cargo left on a sold hull is destroyed.

### Destruction & Escape Pods

Losing a fight normally leaves your ship **disabled**, not destroyed. But if you enter combat with **0 shields, 0 fighters, and 0 torpedoes** and lose, the ship is **destroyed**: the hull and everything installed on it are gone, cargo is lost, and your remaining turns are wiped. Your escape pod puts you at a planet where you own a built Starbase — otherwise Sector 0 — and reactivates your first surviving Hangar ship, or grants a free SS Starter if you have none. A warning banner appears whenever your defenses are fully depleted; don't fly past it. Full details in [Combat](/guide/combat/).

### Maintenance & Repair

Two repair paths, plus free recovery:

- **Port repair** (the Repair service at Stardock, Federation, Standard, Depot, and Mining ports, plus dedicated Repair Stations): restores everything — shields, fighters, and torpedoes — with no turn cost (minimum 200 cr). The only repair that replenishes your consumables.
- **Shipyard and field-kit repair**: shields only. A field kit works anywhere while disabled (2 turns, shields to 50%); the starport shipyard restores full shields for 1 turn. Fighters and torpedoes are re-bought at the starport weapon bays.
- **Disabled ships auto-recover** for free to 50% shields at the next 4-hour turn boundary.

There is no refueling. Ships don't consume fuel — movement costs turns, and "fuel" is just a trade commodity.

## Credits & Economy

Credits are the universal currency. Earn them through:

- **Trading**: buy commodities cheap, haul them to a port type that pays more
- **Missions**: complete objectives for credits and XP
- **Combat**: loot credits from defeated ships (PvP victories loot credits, not cargo)
- **Planets**: develop planets and earn passive income from Trading Posts
- **Bounties**: collect player and faction bounty contracts
- **Exploration**: ruins, anomalies, and first-visit XP

Spend them on cargo, ships, permanent upgrades, deployables, and services. And if you run dry mid-cycle: **agricultural ports sell provisions** — 800 cr per turn restored, max 5 per purchase.

## Banking

Your wallet is at risk; your bank is not. Banked credits are safe from **combat looting** and from **bounty arrest** (an arrest seizes only your wallet). Deposits and withdrawals are free, cost no turns, and are available at starports and at ports with a Banking service (Stardock and Federation ports).

One caveat: ship repair can auto-draw from your bank if your wallet is short — shipyard repair charges a 10% fee on the shortfall it covers.

## Factions & Alignment

Two separate scores shape how the galaxy treats you:

- **Alignment** (−1000 to +1000): your Federation-vs-Pirate standing. Moved by missions, combat, smuggling busts, port and planet attacks and claims — **not** by ordinary trading.
- **Trader reputation** (0–100): your merchant standing, built through dealings with NPC traders you meet in space (not port trades). Affects prices at every port.

What alignment does: faction port pricing (up to 20% off when friendly, +50% markup when hostile), NPC behavior (pirates and patrols flip aggressive around ±300), and docking rights at the two faction starports (denied past ∓300 — regular ports never turn you away). One thing it does **not** do: gate ship purchases. Ship availability is by location — the Federation starport stocks Federation hulls, the Pirate starport stocks Pirate hulls.

**PvP** is territory-gated: Federation territory is always safe; everywhere else is fair game when the season has PvP enabled (the default). See [Galaxy & Territory](/guide/galaxy-territory/) and [Reputation & Factions](/guide/reputation-factions/).

## Corporations

Players can band together in **corporations** — founded for 50,000 cr, with private chat, a shared corp bank, a ship pool, a corp Starbase, and fleets of up to 3 ships that attack together. Your corp hub lives on the **Ship tab, under Corps**. Full coverage — roles, joining policies, fleets, and loot rules — is in [Corporations & Fleets](/guide/corporations-fleets/).

## Tips

- Bank your credits when you're done for the session — safe from looters and bounty hunters alike
- Federation space is safer for new pilots; move outward as you grow
- Upgrade cargo holds early — the tiers cost only credits, no XP gates, and more holds means more profit per run
- Pirate hulls have identical stats and prices to their Federation mirrors but +10 escape — worth it if you can dock at the pirate starport
- You can hold only **one mission at a time** — finish or abandon it (no penalty) before taking another
- When turns run out mid-cycle, provisions at an Agricultural Station are the only way to buy more
