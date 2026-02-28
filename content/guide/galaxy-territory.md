---
title: "Galaxy & Territory"
date: 2026-02-28
draft: false
description: "How galaxies are structured, territory types, and what each zone means"
weight: 2
toc: true
---

Every season takes place in a procedurally generated galaxy. It is a web of interconnected sectors with distinct territory types, regions, and rules.

## Galaxy Structure

The galaxy is divided into **sectors** connected by navigation links. Each sector has a sector number, a territory type (federation, neutral, or pirate), a region (from FED_CORE at the center to DEEP and PIRATE at the edges), and points of interest like ports, planets, landmarks, and wormholes.

Navigation between sectors follows the link network. Every sector has between 2 and 4 neighbors. You move one sector at a time for 1 turn, or use a **warp drive** to jump multiple sectors at once.

## Territory Types

Territory is the most important property of a sector. It determines what you encounter, what is legal to carry, and what services are available.

### Federation Space

Safe, law-abiding, and actively patrolled.

- Pirate NPCs never attack first
- Patrol NPCs enforce contraband laws
- Carrying contraband here is illegal and will trigger customs scans
- Ports include standard trading, Federation Starports, Tech Hubs, and repair stations
- PvP is never enabled here, regardless of galaxy settings
- New players spawn here

### Neutral / Unincorporated Space

The frontier between civilization and lawlessness.

- Pirate NPCs attack first 33% of the time
- Contraband is still illegal and patrol NPCs operate here
- Ports include a mix of trading ports and independent stations
- PvP is enabled when the galaxy has PvP turned on

### Pirate Space

No law. High risk, high reward.

- Pirate NPCs attack first 66% of the time
- Contraband is legal to carry with no customs enforcement
- Ports are pirate bases, black markets, and service stations only. Regular trading ports do not exist in pirate space.
- PvP is enabled when the galaxy has PvP turned on

## Regions

Regions describe where a sector sits in the galaxy's geography. They affect NPC spawn rates and difficulty.

| Region | Description | Danger |
|--------|-------------|--------|
| FED_CORE | Federation heartland | Minimal |
| FED_SPACE | Federation territory | Low |
| INNER | Inner systems | Low to Medium |
| CORE | Central hub systems | Medium |
| FRONTIER | Edge of known space | Medium |
| OUTER | Outer rim | High |
| PIRATE | Pirate-controlled | Very High |
| DEEP | Deep space | Extreme |
| NEBULA | Nebula sectors | Variable |

Higher-tier NPC ships appear in more dangerous regions. A Pirate tier 5 Warlord Battleship only shows up in PIRATE or DEEP space.

## Reading the Nav Screen

The Nav screen displays your current sector and its connections. Key information:

- **Territory badge** shows federation, pirate, or neutral status and whether PvP is active (shield icon means safe, sword icon means PvP enabled)
- **Sector number** is your unique sector identifier
- **Neighbor grid** shows connected sectors you can move to directly
- **Points of interest** lists ports, planets, and other features in this sector
- **Players indicator** shows other players currently in this sector, visible in PvP zones

## Warp Drive

Once you install a warp drive (available at starport shipyards), you can jump directly to any sector you have previously visited, regardless of how far away it is.

- Warp costs turns based on distance
- The Warp Optimizer tech upgrade reduces warp turn cost by 1
- Warp can be interrupted by NPC encounters mid-route
- You cannot warp to sectors you have not visited yet

## Sector History

Every sector you visit is recorded in your sector history. This powers warp targeting, the recent sectors list on the Nav screen, and beacon tracking. Your history persists for the life of the season and resets when a new season starts in a new galaxy.
