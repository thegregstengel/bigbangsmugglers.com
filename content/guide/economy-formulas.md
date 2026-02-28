---
title: "Economy Formulas"
date: 2026-02-28
draft: false
description: "Precise game formulas for power users"
weight: 12
toc: true
---

For players who want to optimize every credit. These formulas come directly from the game backend.

## Trade Price Calculation

Prices use a logistic curve based on stock ratio.

```
stockRatio = currentStock / maxStock  (0.0 to 1.0)

L_range = L_max - L_min
normalized = (stockRatio * L_range + L_min)
price_multiplier = 1 / (1 + e^(-k * (normalized - L_midpoint)))

rawPrice = price_multiplier * BASE_PRICE[commodity]
```

**Port type parameters:**

| Port Type | L_min | L_max | Spread |
|-----------|-------|-------|--------|
| Standard | 0.60 | 2.20 | 10% |
| Fuel Depot / Agri | 0.80 | 1.40 | 6% |
| Tech Hub | 0.50 | 2.60 | 15% |
| Black Market | 0.40 | 3.00 | 22% |
| Pirate Base | 0.40 | 2.80 | 20% |
| Federation Port | 0.70 | 1.80 | 8% |

**Base commodity prices:** Fuel 10 cr, Organics 15 cr, Equipment 25 cr (multiplied by the port-type factor)

**Sell price:** `sellPrice = floor(buyPrice * (1 - spread))`

**Daily noise:** Random variance per day where sigma is 0.5% for Low volatility, 1.0% for Medium, and 1.8% for High.

**Price bands (hard limits):**

| Commodity | Min | Max |
|-----------|-----|-----|
| Fuel | 60 cr | 220 cr |
| Organics | 90 cr | 350 cr (approx) |
| Equipment | 150 cr | 600 cr (approx) |

## Combat Power Formula

```
rawPower = basePower + (fighters × 0.8) + (shields × 1.2) + (torpedoes × 2.0)
effectivePower = rawPower × roleMultiplier × regionMultiplier × xpMultiplier
winProbability = attackerPower / (attackerPower + defenderPower)
```

Role multipliers vary slightly by ship class, ranging from 1.00 to roughly 1.10 for most ships.

**Region bonuses:**

- Federation-aligned ships defending in Fed Core: +10%
- Federation-aligned ships defending in Fed Space: +5%

Both sides receive a small random multiplier before resolution to prevent fully deterministic outcomes.

## Loot Calculation

```
creditsLooted = min(loser.credits * 0.25, winner.tier.creditCap)
cargoLooted = floor(loser.totalCargo * 0.30)
```

**Credit caps by ship tier:**

| Tier | Credit Cap |
|------|-----------|
| 1 to 2 | 5,000 cr |
| 3 | 15,000 cr |
| 4 | 40,000 cr |
| 5 | 100,000 cr |
| 6 | 200,000 cr |

## Planet Production

```
factoryMultiplier = 1 + (0.15 * factoryLevel)
populationMultiplier = 0.2 + ((population / populationCap) * 0.8)

dailyFuel      = floor(80  * factoryMultiplier * populationMultiplier)
dailyOrganics  = floor(60  * factoryMultiplier * populationMultiplier)
dailyEquipment = floor(30  * factoryMultiplier * populationMultiplier)
```

**Population growth (daily):**

```
baseGrowth = 10
growthMultiplier = 1 + (0.10 * habitatLevel)
attrition = floor(population * 0.01)
growth = floor(baseGrowth * growthMultiplier - attrition)
newPopulation = min(population + growth, populationCap)
```

## Structure Upgrade Costs

```
cost = floor(baseCost * multiplier^(currentLevel - 1))
```

| Structure | Base Cost | Multiplier |
|-----------|-----------|------------|
| Warehouse | 5,000 cr | 1.8x |
| Habitat | 6,000 cr | 1.8x |
| Factory | 7,500 cr | 1.8x |
| Shield Generator | 10,000 cr | 2.0x |

**Factory upgrade cost by level:**

| Level | Level Cost | Cumulative |
|-------|-----------|------------|
| 1 | 7,500 | 7,500 |
| 2 | 13,500 | 21,000 |
| 3 | 24,300 | 45,300 |
| 4 | 43,740 | 89,040 |
| 5 | 78,732 | 167,772 |

## NPC Spawn Rates

Effective spawn rate per move equals baseRate multiplied by regionMultiplier multiplied by galaxyEncounterRate.

**Base rates:** Pirate 5%, Trader 3%, Patrol 2%

**Key region multipliers:**

| Region | Pirate | Trader | Patrol |
|--------|--------|--------|--------|
| FED_CORE | 0.2x | 1.5x | 3.5x |
| FED_SPACE | 0.4x | 1.5x | 3.0x |
| FRONTIER | 1.2x | 1.0x | 0.5x |
| PIRATE | 2.0x | 0.3x | 0.1x |
| DEEP | 1.3x | 0.2x | 0x |

## Contraband Detection

```
baseThreshold = 0.75   (75% chance of detection)
withCloakingDevice = 0.25   (25% chance)

roll = random(0, 1)
caught = (roll < threshold)
```

The cloaking device is consumed whether or not you are caught. One device per scan event. The 30-minute cooldown is shared between patrol scans and port customs scans.

## Tech Upgrade Effects

| Upgrade | Effect Formula |
|---------|---------------|
| Cargo Compressors | holds += floor(holds * 0.20) |
| Shield Booster | shields += floor(shields * 0.15), upgrades.shields += bonus |
| Escape Pods | escape = min(0.95, escape + 0.15) |
| Combat AI | +20% fighter coefficient in combat (flag) |
| Stealth Plating | -30% detection threshold (flag) |
| Warp Optimizer | warpTurns -= 1 (flag) |
