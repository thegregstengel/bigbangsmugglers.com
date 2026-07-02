---
title: "Galaxy & Territory"
date: 2026-07-02
draft: false
description: "How galaxies are structured, the six regions, territory types, and where PvP actually happens"
weight: 3
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

Every season takes place in a procedurally generated galaxy: a web of interconnected sectors organized into six regions by distance from the center, with a territory overlay that determines law, ports, and who will shoot at you. Understanding the geography is the difference between a safe trade run and an ambush in the rim.

## Galaxy Structure

The galaxy is a grid of **sectors**. Sizes are chosen when the season is created: small (1,024 sectors), medium (4,096), large (16,384), or massive (65,536). Sectors are numbered by distance from the center — **Sector 0 is the exact center of the galaxy**, and the highest numbers sit on the outer rim. A low sector number means you are close to civilization; a high one means you are a long way from help.

New players spawn at Sector 0, home of the Federation Starport.

### Sector Links

Movement follows the link network. Every sector links to its 2–4 adjacent grid neighbors (4 in the interior, fewer on the edges and corners), and some sectors have more:

- About 1 in 5 sectors also links to its diagonal neighbors.
- Federation Core sectors sometimes carry a long-range **Federation highway** link to a distant part of the galaxy.
- Outer Rim sectors sometimes carry a one-way **smuggling route** exit to a random sector.

Not every link works in both directions. Diagonal shortcuts, highways, and smuggling routes may be traversable from one side only — if you take an unusual exit, don't assume you can retrace your steps. Plan your return route before you commit.

Each sector can hold points of interest — ports, planets, stations, landmarks — described in the [Locations guide](/guide/locations/). Wormholes are a special case: they only appear when you're standing in one of their endpoint sectors.

## The Six Regions

Regions are bands of distance from the galactic center. They set NPC spawn rates and mark where PvP is possible. From the safe core to the lawless rim:

| Region | Where (distance from center) | Character |
|--------|------------------------------|-----------|
| FED_CORE | Innermost 10% | Federation heartland. Heavy patrols, zero pirates. Safe zone. |
| FED_SPACE | 10–25% out | Federation-adjacent space. Well patrolled, still no pirates. |
| INNER | 25–45% out | The first pirates appear (weak ones). Patrols still common. |
| MIDDLE | 45–70% out | The working middle of the galaxy. Pirates at full strength, patrols thinning. |
| OUTER | 70–90% out | **PvP zone.** Pirates common, patrols nearly gone. |
| OUTER_RIM | Outermost 10% | **PvP zone.** The most dangerous pirates in the game, no patrols at all, and one-way smuggling routes. |

There is no separate "danger rating" stat — danger in a region is the product of who spawns there, at what strength, and whether other players can attack you.

## Territory: Federation, Neutral, Pirate

Territory is an independent overlay on top of regions. The **innermost ~5% of sectors are Federation territory**, the **outermost ~5% are Pirate territory**, and everything in between is **Neutral Space** (the exact percentages can vary per galaxy). Territory determines law and infrastructure:

### Federation Space

- **Pirates never appear here.** Not "won't attack first" — they do not spawn at all.
- Patrols are everywhere and enforce contraband law. Federation-type ports run customs scans when you open their trade screen.
- All the lawful port types operate here, and the Federation Starport sits at Sector 0.
- **No PvP, ever** — Federation territory sits deep inside the safe core.

### Neutral Space

The vast middle of the galaxy. Contraband is still illegal — patrols operate here (thinning as you head outward) and Federation-type ports still run customs. Both pirates and patrols spawn, at rates set by the region you're in.

Most of Neutral Space is PvP-free. Only the neutral sectors that fall in the OUTER and OUTER_RIM regions allow PvP (see below).

### Pirate Space

The outer band. No law of any kind:

- **Patrols never spawn here**, and there is no customs enforcement — contraband is effectively legal.
- The only ports are pirate bases and black markets. None of the lawful port types generate in Pirate territory, and black markets generate *only* here.
- The Pirate Starport sits in the middle of the pirate band.
- Pirate NPCs are at their most aggressive (see the ambush table below).

## Where PvP Happens

PvP is gated by **region, not territory**: when a galaxy has PvP enabled, players can attack each other **only in the OUTER and OUTER_RIM regions** — the outer bands of the galaxy. Federation space and most of Neutral Space (everything through the MIDDLE region) are PvP-free no matter what the galaxy settings say.

Practical version: your sector's territory badge tells you the law, but your distance from the center tells you whether another player can shoot you. If you're carrying a fortune, stay out of the outer bands or take a wormhole.

## NPCs by Region

Every move rolls a small chance of an NPC encounter. Three types roam the galaxy — pirates, Federation patrols, and traders — and where they concentrate follows the geography:

- **Patrols** are thickest in the core (about 4× their base rate in FED_CORE, 3.5× in FED_SPACE), thin out through the middle, and are completely absent from the OUTER_RIM. They never spawn in Pirate territory.
- **Pirates** don't exist in FED_CORE or FED_SPACE, appear weakly in INNER, and ramp up to 2× their base rate in the OUTER_RIM. They never spawn in Federation territory.
- **Traders** are most common in the settled middle of the galaxy and scarce in the rim.

Pirate ships also get tougher the further out you go: tiers 2–3 in INNER, 2–4 in MIDDLE, 3–4 in OUTER, and 3–5 in the OUTER_RIM. The tier 5 **Warlord Battleship** — the biggest pirate NPC in the game — spawns only in the OUTER_RIM.

> **Naming trap:** the NPC "Warlord Battleship" (tier 5 pirate encounter) is a different ship from the **Warlord**, the tier 3 pirate raider players can buy at the Pirate Starport. Seeing a Warlord on the ship catalog does not mean you can fly the thing that ambushed you in the rim.

### Pirate Ambush Odds Depend on YOUR Standing

Whether a spawned pirate attacks first depends on your faction alignment and where you are:

| Your alignment | Neutral Space | Pirate territory |
|----------------|---------------|------------------|
| Pirate-aligned (below −300) | Never ambushed | Never ambushed |
| Neutral | 33% | 66% |
| Federation-aligned (above +300) | 66% | Always |

Two overrides: if you carry an active **pirate syndicate bounty**, pirates attack on sight regardless of alignment; if you carry an active **federation bounty**, patrols attack on sight. See [NPCs](/guide/npcs/) for what happens once an encounter fires.

## Reading the Nav Screen

The Nav screen shows your current sector and everything in it:

- **Territory badge** — Federation, Neutral, or Pirate, with a shield icon (safe) or sword icon (PvP possible here).
- **Sector number** — remember, lower = closer to the center.
- **"Warp to" section** — despite the name, these buttons are **ordinary 1-turn moves** to adjacent sectors. The actual warp drive is the separate Warp Drive card.
- **Points of interest** — ports, planets, stations, and landmarks in this sector, plus a Wormholes card when one is present.
- **Players list** — every player with an active, undocked, unlanded, uncloaked ship in your sector, wherever you are. This list appears in all regions, not just PvP zones — in safe space it's information, in the outer bands it's a target list (yours and theirs).

## Warp Drive

A warp drive lets you jump multiple sectors in one action. Install one at a Starport shipyard for **15,000 cr** (requires a Tier 2+ ship and 100 XP); upgrades cost (next level × 15,000) cr up to level 5.

- **Visited sectors only.** You can warp to any sector already in your sector history. Tavern intel and Nav Beacon landmarks also add sectors to your history without visiting — see [Scanners & Intel](/guide/scanners-intel/).
- **Cost**: turns = hops ÷ warp level, rounded up, minimum 1. The Warp Optimizer tech upgrade takes 1 more off (still minimum 1).
- **Interruptions**: each hop has a small chance (about 5% on short jumps, capped near 30% across an entire journey) of an NPC encounter that halts the warp in that sector. Any NPC stops you, but only an auto-aggressive pirate forces combat — a patrol or trader just leaves you stranded mid-route. Unused turns are refunded proportionally.
- **Arrival is not free**: enemy mines, sector defenses, and limpet trackers at the destination all still trigger. Hazards, however, never damage a warping ship — hazard damage only applies to plain moves.

The **Tesseract Drive** (10,000,000 cr, Tier 5 hull, level 100) is the endgame alternative: a flat **25 turns** to jump to any visited sector, any distance, with **zero chance of interruption**. Destination mines, defenses, and limpets still apply.

**Wormholes** are the third long-distance option — 1 turn, and the only travel that triggers nothing at all on arrival. See [Locations](/guide/locations/) for how they work.

## Sector History & the Explored Map

Every sector you visit is recorded: first visit, last visit, visit count, and what's there. Your history powers warp targeting, the Recent Sectors list on the Nav screen (your 8 most recent), and beacon tracking. It persists for the life of the season and starts fresh with the next galaxy.

Exploration pays: your **first visit** to a sector awards XP — 10 base, +25 if it has a port, +50 for a planet, +100 for a landmark (scaled by the galaxy's XP multiplier).
