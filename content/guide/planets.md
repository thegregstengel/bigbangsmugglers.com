---
title: "Planets"
date: 2026-02-28
draft: false
description: "Claim and develop planets for passive income and strategic control"
weight: 9
toc: true
---

Planets are the late-game cornerstone of Big Bang Smugglers. Claim one, develop it with structures, and it generates daily commodities you can collect and sell: passive income while you trade, fight, and explore.

## Claiming a Planet

To claim a planet:
1. Navigate to a sector with an unclaimed planet (visible on the Nav screen as a POI)
2. Open the planet from the sector's points of interest
3. Tap **Claim Planet**

**Requirements:**
- Planet must be unclaimed (no current owner)
- You must be in the sector with the planet

Once claimed, the planet is yours. Your name appears as the owner and it becomes visible on the galaxy feed.

## Colonizing with Workers

Workers increase your planet's **population**, which directly scales production output.

**How to get workers:** Purchase Mining Workers at any Starport under the Supply/Recruitment section.

**How to deploy:** Open your planet, tap **Deploy Workers**. Workers transfer from your inventory to the planet's population.

**Population mechanics:**
- Starting population: 50
- Population cap: 500 (base), expandable with Habitat structures
- Daily growth: ~10 workers per day × Habitat level bonus, minus 1% attrition
- Population multiplier: scales production from 20% (empty) to 100% (at cap)

At full population cap your planet produces roughly **5x more** than an empty one.

## Structures

Build structures to increase production capacity, storage, population cap, and garrison strength. Each structure type levels up independently.

| Structure | Base Cost | Cost Multiplier | Effect |
|-----------|-----------|-----------------|--------|
| Warehouse | 5,000 cr | 1.8× per level | +2,000 storage capacity per level |
| Habitat | 6,000 cr | 1.8× per level | +250 population cap per level |
| Factory | 7,500 cr | 1.8× per level | +15% production multiplier per level |
| Shield Generator | 10,000 cr | 2.0× per level | Garrison defense bonus |

**Cost formula:** `baseCost × 1.8^(currentLevel)`: each level costs 80% more than the last.

**Example: Factory upgrade costs:**
- Level 1: 7,500 cr
- Level 2: 13,500 cr
- Level 3: 24,300 cr
- Level 4: 43,740 cr

Factories compound fast: higher levels are expensive but scale production dramatically.

## Daily Production

Planets generate commodities every 24 hours (daily tick). Production is calculated as:

```
factoryMultiplier = 1 + (0.15 × factoryLevel)
populationMultiplier = 0.2 + ((population / populationCap) × 0.8)
totalMultiplier = factoryMultiplier × populationMultiplier

daily fuel     = floor(80  × totalMultiplier)
daily organics = floor(60  × totalMultiplier)
daily equipment = floor(30 × totalMultiplier)
```

**Example: Fully developed planet (Factory 3, full population):**
- factoryMultiplier = 1 + (0.45) = 1.45
- populationMultiplier = 1.0 (full pop)
- daily fuel: 116 units | organics: 87 units | equipment: 43 units

At standard port prices (~150 cr/fuel, ~200 cr/organics, ~400 cr/equipment):
**~53,600 cr/day** from a well-developed planet.

## Collecting Production

When production is ready (24 hours after the last collection):
1. Navigate to your planet's sector
2. Open the planet
3. Tap **Collect Production**

Collected commodities go directly into your ship's cargo hold. Make sure you have enough free holds: excess production stays in planet storage until you collect it.

**Storage cap:** Base 1,000 units, +2,000 per Warehouse level. Production accumulates in storage if not collected: useful for batching collection runs.

## Planet Storage

Beyond daily production, you can manually **deposit** and **withdraw** commodities from your planet's storage:

- **Deposit:** Transfer cargo from your ship into planet storage
- **Withdraw:** Pull stored commodities back into your ship's hold
- Useful for stockpiling before a trade run or hiding credits-worth of goods

## Garrison Fighters

Garrison fighters defend your planet from attack. To garrison:

1. Purchase fighters at any Starport (Recruitment section)
2. Navigate to your planet
3. Tap **Garrison Fighters**: transfers from your ship's fighter bay to the planet

Garrison fighters engage automatically when someone attacks your planet. Shield Generator structures increase garrison defense effectiveness.

## Planet Attacks

Other players can attack your planet to steal stored commodities or attempt to claim it from you. Defense depends on:
- Your garrison fighter count
- Shield Generator level
- The attacker's combat stats

Keep your garrison stocked and check your planet's feed notifications if you're away.

## Strategic Notes

- **Location matters:** Planets in pirate space are more exposed to attacks but no customs scans if you're running contraband through that zone
- **Proximity mines** can be deployed in sectors where you own a planet: a first line of defense before garrison engages (see [Beacons & Mines](/guide/beacons-mines))
- **Collect regularly:** Storage caps limit how much can accumulate; uncollected production after the cap is wasted
- **Workers first:** Don't build factories until you have enough population to benefit: the population multiplier has a bigger impact at low levels than factory upgrades
