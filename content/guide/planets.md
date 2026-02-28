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

## Trading Posts

A Trading Post is a player-built port that lets other captains buy commodities from your planet. It is a late-game investment — expensive to build, but it generates passive income while you do other things.

### Building a Trading Post

You need two things before you can build:

- Warehouse Level 2 on the planet
- 100,000 credits in your wallet or bank

Open your planet screen, go to the Trade tab, and tap Build Trading Post. The cost comes from your wallet first, then your bank if the wallet falls short. The post is permanent and cannot be demolished.

### How It Works

Once built, the Trading Post appears in your sector as a named port on the Nav screen. Any player who enters the sector can open it and buy commodities. The post is buy-only — players cannot sell to it.

Stock transfers from your planet storage to the post every 4 hours at the same boundaries as turn resets. You can also trigger a manual refill from the Trade tab once per 4-hour window. If your planet storage is empty, the post runs dry until production refills it.

You earn 80% of every sale, deposited directly to your bank. The remaining 20% covers operational costs.

### Upgrade Levels

The post starts at Level 1 and can be upgraded up to Level 5. Higher levels hold more stock and your prices move closer to standard market rates, which means better margins per sale.

| Level | Upgrade Cost | XP Required | Stock Cap | Price vs Standard |
|-------|-------------|-------------|-----------|------------------|
| 1 | 100,000 cr (build) | None | 100 units | 50% below |
| 2 | 50,000 cr | 5,000 | 250 units | 40% below |
| 3 | 150,000 cr | 15,000 | 500 units | 30% below |
| 4 | 400,000 cr | 40,000 | 1,000 units | 20% below |
| 5 | 1,000,000 cr | 100,000 | 2,000 units | 10% below |

The total investment to reach Level 5 is 1,700,000 cr and 160,000 XP. A max-level post running at full stock is a significant passive income source.

### Robbery

Pirate-aligned captains (alignment score of negative 500 or lower) can attempt to rob your Trading Post if they are in the same sector.

Base success chance is 40%. A Goods Cloaking Device adds 15% to their odds and is consumed on the attempt. Each tier of garrison fighters on your planet (100 fighters per tier, up to 5 tiers) reduces their chance by 5%. Success is capped between 10% and 75% regardless of modifiers.

On a successful robbery the attacker steals up to 30% of your current stock per commodity. Stolen goods are flagged as contraband in their hold.

Every attempt — success or failure — triggers a galaxy-wide feed announcement naming the attacker and your post. Failed attempts are still visible to everyone and a natural reason for other players to post a bounty on the attacker.
