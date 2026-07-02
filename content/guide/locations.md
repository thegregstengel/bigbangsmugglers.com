---
title: "Locations"
date: 2026-07-02
draft: false
description: "Ports, landmarks, stations, starbases, hazards, and wormholes — every point of interest in the galaxy"
weight: 16
toc: true
aliases: ["/guide/descriptions/"]
---

*Accurate as of v1.22.0 (July 2026).*

Every sector can contain points of interest beyond the standard travel links: ports where you trade, landmarks you can interact with for loot and shortcuts, stations with specialized services, and hazards best learned before they learn you. Ports, planets, stations, and landmarks appear on the Nav screen when you enter a sector. Wormholes show up only when you're standing at one of their endpoints. Starbases live on the planet screen, and hazards don't announce themselves at all — more on both below.

---

## Ports

Ports are where you buy and sell fuel, organics, and equipment. Every port type trades all three commodities — specialization is in the prices, not the shelves. Each type charges a fixed price per commodity, and selling at the same port returns 10% less than you paid, so profit comes from hauling goods between port types that value them differently. The full price table and route math live in the [Trading guide](/guide/trading/).

Standard ports offer trading and nothing else. Ship purchases, mission boards, and recruitment are Starport exclusives — see [Starports](/guide/starports/).

### Port Types

| Port type | How common | Beyond trading |
|-----------|------------|----------------|
| **Stardock** | One per galaxy, at Sector 0 | The central hub: banking, repair, ship upgrades, and a tavern |
| **Federation Port** | ~5% of sectors | Banking and repair — and customs scans (see below) |
| **Standard Port** | ~10% of sectors (the most common port in the game) | Trading only |
| **Fuel Depot** | ~3% of sectors | Trading only — its niche is the cheapest lawful fuel |
| **Agricultural Station** | ~3% of sectors | The only ports that sell **turns**: provisions at 800 cr per turn, max 5 per purchase. Cheapest organics in lawful space |
| **Tech Hub** | ~2% of sectors | Ship upgrades (the Tech Hub catalog — see [Tech Upgrades](/guide/tech-upgrades/)) and repair. Found anywhere outside pirate territory |
| **Mining Station** | ~1.5% of sectors | Cheap fuel — and the best organics prices in the galaxy, if you're selling |
| **Research Complex** | ~1% of sectors | Equipment-heavy stock at friendly prices |
| **Pirate Base** | ~1.5% of sectors, pirate and unincorporated space | Black Market shop and a tavern; no questions about your manifest |
| **Black Market** | ~7% of pirate-territory sectors | The cheapest goods anywhere — but everything you buy here is flagged as **contraband** |

None of the lawful port types generate inside pirate territory, and black markets generate only there. If you want the galaxy's cheapest fuel and equipment, you're going to the rim — see [Smuggling](/guide/smuggling/) before you load up.

**Customs**: Federation-type ports scan your cargo for contraband the moment you open their trade screen (at most once per 30 minutes). Getting caught costs you the cargo, a fine, and alignment. Details in the [Smuggling guide](/guide/smuggling/).

**Taverns**: found at the Stardock and pirate ports. Two services: hire mercenary fighters (50 cr each, up to 30 per hire) and **buy intel** — 500 cr reveals 5 sectors you've never visited and makes them warp-eligible, one of only two ways to warp somewhere you've never been (the other: activating a Nav Beacon landmark). See [Scanners & Intel](/guide/scanners-intel/).

### Player-Built Trading Posts

Captains who own planets can build a trading post in their planet's sector. On the Nav screen it appears as a port named **"{Planet} Trading Exchange ({Owner})"** — if you see one, someone invested at least 100,000 credits and a developed planet to put it there.

For visitors, trading posts are **buy-only** — you cannot sell to them. What makes them worth a detour is pricing: a trading post's price ceilings sit **below standard market maximums**, with the discount largest at new posts and shrinking as the owner upgrades — upgrades move prices toward standard rates in exchange for far more stock. Their price scale is genuinely cheaper than any generated port's.

Stock comes only from the owner's planet production, transferred on a **4-hour restock cycle** (the owner can also trigger one manual refill per cycle). Empty shelves mean the planet hasn't produced enough or shoppers beat you to it — check back after the next cycle boundary.

See the [Planets guide](/guide/planets/) for building and operating one.

---

## Landmarks

Landmarks are fixed points of interest scattered across the galaxy — and they are not just scenery. Every landmark offers an interaction, each with its own per-player cooldown per landmark. Since cooldowns are per landmark, knowing where several of them sit turns into a farming rotation.

**Ancient Ruins** — *Explore: 2 turns, 24-hour cooldown.*
The most common landmark. Exploring rolls on a weighted loot table: usually credits (500–5,000) or salvaged equipment paid out in credits, sometimes research data worth XP, occasionally nothing at all — and a rare jackpot of 10,000–25,000 credits. Nobody knows who built them; the payouts suggest they were doing well.

**Space Anomalies** — *Investigate: free, 6-hour cooldown.*
The catch-all category for things the instruments measure but cannot describe. Investigating is free and random: boons include credits (2,000, rarely 8,000), a burst of XP, or **+3 turns**; banes include shield damage (−30), lost fighters (−10), or a forced jump to a random sector. Free to spin, not free of consequences.

**Black Holes** — *Transit: 1 turn, 24-hour cooldown.*
Rare, and the sector remains passable. The interaction is a 1-turn jump to a random sector (often toward the inner galaxy) — with a 20% chance of taking 10–40 shield damage on the way through. A shortcut for captains who trust their shields more than their patience.

**Navigation Beacons** — *Activate: free, 1-hour cooldown.*
Automated relay stations from the early exploration era, still running. Activating one reveals up to 8 adjacent sectors into your sector history — meaning you can **warp to them without ever having visited**. Free map knowledge; take it every time you pass one.

---

## Stations

Stations are smaller than starports and bigger than an excuse to stop. Three types, each with one specialized service:

**Defense Stations**
Federation military installations that sell protection: **4,000 cr buys a 2-hour PvP-immunity contract**. While it runs, other players cannot attack you — and you cannot attack them — and enemy mines and sector defenses won't trigger on you either. Contracts stack on top of any immunity you already have. If your wallet is short, the bank covers the difference at a 10% fee. Cheap insurance for hauling a fortune through the outer bands.

**Repair Stations**
Independent repair outside starport facilities: a repair station restores shields, **fighters, and torpedoes** to maximum — the same full-restock Repair service offered at Stardock and Federation ports. Cost is per unit of damage (5 cr per shield, 10 per fighter, 15 per torpedo, minimum 200 cr), adjusted by your reputation.

**Research Stations**
Scientific facilities in isolated sectors. Their service is **Sector Intelligence**: 300 cr buys the locations of 3 random points of interest — ports, starports, wormholes, or landmarks — somewhere in the galaxy. See [Scanners & Intel](/guide/scanners-intel/) for how it compares to tavern intel.

---

## Starbases

A Starbase is the capstone structure of a fully developed planet: once all six planetary structures reach level 5, the owner can build one for **1,500,000 credits** (wallet only — the bank won't cover this one). One per player (a build cap — capturing another player's Starbase planet can put you over it), permanent, cannot be moved.

One thing to know before you go looking: **Starbases do not appear on the Nav screen or on scans.** A Starbase is part of its planet — you'll find it on the planet screen's Structures tab, and nowhere else.

### Personal Starbase

What the owner gets:

- **Credit vault** — credit storage separate from your bank, usable only while your active ship is in the Starbase's sector. Unlimited capacity.
- **Item vault** — stores six inventory item types: workers, fighters, beacons, mines, ship cloaking devices, and goods cloaking devices. Same in-sector requirement. Note this is *inventory* storage — cargo commodities don't go in the vault.
- **Hangar** — switch between your ships here, the only place besides a Starport that allows it.
- **Respawn point** — if your ship is destroyed, your escape pod returns here instead of Sector 0.

The vault is strictly owner-only — even corpmates can't touch it.

### Corporation Starbase

There's no separate corp Starbase structure: when a Starbase planet belongs to a corporation, the Starbase doubles as corp infrastructure.

- **Ship pool** — members donate spare ships into the pool and any corp member can claim one when in the sector. Claimed ships arrive inactive; switch to them at the hangar.
- **Corp asset vault** — a shared store any corp member can draw from. (Fleet combat pays out in credits to the corp bank, not cargo — see [Corporations & Fleets](/guide/corporations-fleets/).)

Access follows two simple rules: the vault belongs to the planet's owner, everything else follows corp membership — there is no officer-level gatekeeping. See [Corporations & Fleets](/guide/corporations-fleets/).

One more thing: Starbases are spoils of war. If the planet is captured, the Starbase — vault contents included — changes hands intact.

---

## Hazards

Some sectors contain environmental hazards. Here is the honest version: **hazards are not currently shown anywhere in the UI.** No scanner lists them, no sector view flags them — the first you'll hear of one is the damage report after you fly into it. Experienced captains keep a mental map of which sectors bite.

The rules of engagement are simple:

- Hazard damage applies **only when you move into the sector with a plain, one-hop move**. Warp, Tesseract, wormhole, and black-hole travel never take hazard damage.
- Sitting in a hazardous sector is safe. Entering it is what costs.
- Hazards never affect combat.

The five types, from a shrug to a real problem:

**Nebulae** — dense gas clouds. Atmosphere only: no damage, no gameplay effect.

**Ion Storms** — electromagnetic interference. Also atmosphere only, and they don't move — a stormy sector stays stormy.

**Asteroid Fields** — about a 20% chance of 10–20 shield damage each time you move in.

**Radiation Zones** — a flat 25 shield damage every time you move in. Not cumulative exposure — each entry costs the same, and short visits are not free.

**Minefields** — leftover ordnance from forgotten conflicts (distinct from player-deployed mines — see [Deployables](/guide/deployables/)). The nastiest hazard in the game: a 40% chance of 40–60 shield damage on entry, enough to disable a ship that arrives with weak shields and no fighters.

---

## Wormholes

Each galaxy contains a handful of wormholes (5–10) connecting distant sectors. You'll only see one when you're standing in an endpoint sector — the Nav screen shows a Wormholes card with its stability and direction.

Transit costs **1 turn**, regardless of how far the other end is. And here is why they're worth memorizing: wormhole transit is **the safest travel in the game** — it bypasses NPC encounters, enemy mines, sector defenses, and hazards entirely. Nothing is waiting for you on the other side except whatever was already there.

Two caveats:

- About 70% of wormholes are **stable**. The unstable ones occasionally scatter you to a random sector instead of the far endpoint — same turn cost, wrong address.
- Most wormholes work in both directions, but roughly 1 in 5 is **one-way**: usable from one side only, with nothing visible at the far end to warn you there's no ride back.

Like all travel, taking a wormhole breaks your cloak.
