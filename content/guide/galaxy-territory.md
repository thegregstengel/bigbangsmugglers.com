---
title: "Galaxy & Territory"
date: 2026-02-28
draft: false
description: "How galaxies are structured, territory types, and what each zone means"
weight: 2
toc: true
---

Every season takes place in a procedurally generated galaxy — a web of interconnected sectors with distinct territory types, regions, and rules.

## Galaxy Structure

The galaxy is divided into **sectors** connected by navigation links. Each sector has:

- A **sector number** (displayed in the nav grid and on beacons)
- A **territory type** (federation, neutral/unincorporated, or pirate)
- A **region** (from FED_CORE at the center to DEEP and PIRATE at the edges)
- **Points of interest** — ports, planets, landmarks, stations, wormholes

Navigation between sectors follows the link network. Every sector has between 2–4 neighbors. You move one sector at a time (costs 1 turn) or use **warp drive** to jump multiple sectors at once.

## Territory Types

Territory is the most important property of a sector. It determines what you'll encounter, what's legal to carry, and what services are available.

### Federation Space 🛡️

Safe, law-abiding, actively patrolled.

- **NPC aggression:** Pirates never attack first; patrol NPCs enforce contraband laws
- **Contraband:** Carrying it here is illegal — expect customs scans
- **Ports:** Standard trading ports, Federation Starports, Tech Hubs, repair stations
- **PvP:** Never enabled, regardless of galaxy settings
- **New players spawn here**

### Neutral / Unincorporated Space

The frontier between civilization and lawlessness.

- **NPC aggression:** Pirates attack first 33% of the time
- **Contraband:** Still illegal here — patrol NPCs operate in neutral space
- **Ports:** Mix of trading ports and independent stations
- **PvP:** Enabled when the galaxy has PvP turned on

### Pirate Space ⚔️

No law. High risk, high reward.

- **NPC aggression:** Pirates attack first 66% of the time
- **Contraband:** Legal to carry — no customs enforcement
- **Ports:** Pirate bases, Black Markets, and service stations only (no regular trading ports)
- **PvP:** Enabled when the galaxy has PvP turned on

> **Important:** Regular trading ports (standard, agri, depot) do not exist in pirate sectors. The only commercial ports in pirate space are Black Markets and Pirate Bases. Plan your routes accordingly.

## Regions

Regions describe where a sector sits in the galaxy's geography. They affect NPC spawn rates and difficulty:

| Region | Description | Danger |
|--------|-------------|--------|
| FED_CORE | Federation heartland | Minimal |
| FED_SPACE | Federation territory | Low |
| INNER | Inner systems | Low-Med |
| CORE | Central hub systems | Medium |
| FRONTIER | Edge of known space | Medium |
| OUTER | Outer rim | High |
| PIRATE | Pirate-controlled | Very High |
| DEEP | Deep space | Extreme |
| NEBULA | Nebula sectors | Variable |

Higher-tier NPC ships (stronger stats, better loot) appear in more dangerous regions. A Pirate tier 5 Warlord Battleship will only show up in PIRATE or DEEP space — the outer rim.

## Reading the Nav Screen

The Nav screen displays your current sector and its connections. Key information:

- **Territory badge** — Shows federation/pirate/neutral and PvP status (🛡️ = safe, ⚔️ = PvP enabled)
- **Sector number** — Your unique sector identifier
- **Neighbor grid** — Connected sectors you can move to directly
- **Points of interest** — Ports, planets, and other features in this sector
- **Players indicator** — Other players currently in this sector (shown in PvP zones)

## Warp Drive

Once you install a warp drive (available at starport shipyards), you can jump directly to any sector you've previously visited — no matter how far away.

- Warp costs turns based on distance (number of hops in the shortest path)
- The **Warp Optimizer** tech upgrade reduces warp turn cost by 1
- Warp can be interrupted by NPC encounters mid-route
- You cannot warp to sectors you haven't visited yet

## Sector History

Every sector you visit is recorded in your **sector history**. This powers:

- Warp targeting (you can only warp to visited sectors)
- The recent sectors list on the Nav screen
- Beacon tracking (beacons show sector info from when you placed them)

Your history persists for the life of the season. When a new season starts in a new galaxy, history resets.
