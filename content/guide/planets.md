---
title: "Planets"
date: 2026-02-28
draft: false
description: "Claim and develop planets for passive income and strategic control"
weight: 9
toc: true
---

Planets are the late-game cornerstone of Big Bang Smugglers. Claim one, develop it with structures, and it generates daily commodities you can collect and sell for passive income while you trade, fight, and explore.

## Claiming a Planet

Navigate to a sector with an unclaimed planet, which you will see listed as a point of interest on the Nav screen. Open the planet and tap **Claim Planet**. The planet must be unclaimed and you must be in the same sector.

Once claimed, your name appears as the owner and it becomes visible on the galaxy feed.

## Colonizing with Workers

Workers increase your planet's population, which directly scales production output.

Get workers by purchasing Mining Workers at any Starport. To deploy them, open your planet and tap Deploy Workers. Workers transfer from your inventory to the planet's population.

**Population mechanics:**

- Starting population: 50
- Base population cap: 500, expandable with Habitat structures
- Daily growth: roughly 10 workers per day with Habitat level bonus, minus 1% attrition
- Population scales production from 20% output when empty to 100% at the cap

At full population your planet produces roughly five times more than an empty one.

## Structures

Build structures to increase production, storage, population cap, and garrison strength.

| Structure | Base Cost | Cost Multiplier | Effect |
|-----------|-----------|-----------------|--------|
| Warehouse | 5,000 cr | 1.8x per level | +2,000 storage capacity per level |
| Habitat | 6,000 cr | 1.8x per level | +250 population cap per level |
| Factory | 7,500 cr | 1.8x per level | +15% production multiplier per level |
| Shield Generator | 10,000 cr | 2.0x per level | Garrison defense bonus |

Each level costs 80% more than the last. Factory level 3 costs 24,300 cr and level 5 costs 78,732 cr.

## Daily Production

Planets generate commodities every 24 hours. Production formula:

```
factoryMultiplier = 1 + (0.15 × factoryLevel)
populationMultiplier = 0.2 + ((population / populationCap) × 0.8)

daily fuel      = floor(80  × factoryMultiplier × populationMultiplier)
daily organics  = floor(60  × factoryMultiplier × populationMultiplier)
daily equipment = floor(30  × factoryMultiplier × populationMultiplier)
```

A fully developed planet at Factory level 3 with full population outputs 116 fuel, 87 organics, and 43 equipment per day. At standard port prices that is roughly 53,000 cr per day.

## Collecting Production

When production is ready, navigate to your planet's sector, open the planet, and tap Collect Production. Collected commodities go into your ship's cargo hold. Make sure you have enough free holds. Excess production stays in planet storage until you collect it.

**Storage cap:** Base 1,000 units, plus 2,000 per Warehouse level. Production accumulates in storage if not collected, which is useful for batching collection runs.

## Planet Storage

You can deposit cargo from your ship into planet storage and withdraw stored commodities back to your ship's hold. This is useful for stockpiling before a trade run.

## Garrison Fighters

Garrison fighters defend your planet from attack. Purchase fighters at any Starport, navigate to your planet, and tap Garrison Fighters. Fighters transfer from your ship's fighter bay to the planet and engage automatically when someone attacks. Shield Generator structures improve garrison defense effectiveness.

## Planet Attacks

Other players can attack your planet to steal stored commodities. Defense depends on your garrison fighter count, Shield Generator level, and the attacker's combat stats. Keep your garrison stocked and watch your feed notifications.

## Strategic Notes

- Deploy proximity mines in planet sectors as a first line of defense before garrison engages. See [Beacons & Mines](/guide/beacons-mines).
- Collect regularly. Production above the storage cap is wasted.
- Prioritize workers before factories. Population multiplier has a bigger impact at low population levels than additional factory levels.
- Planets in pirate space are more exposed to attacks but carry no contraband enforcement risk.
