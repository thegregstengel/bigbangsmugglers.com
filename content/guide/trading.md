---
title: "Trading & Economy"
date: 2026-02-28
draft: false
description: "Master the art of profitable trading"
weight: 3
toc: true
---

Trading is the backbone of your career. Learn to read the markets, find the spreads, and maximize your credits per turn.

## The Three Commodities

| Commodity | Price Range (buy) | Notes |
|-----------|------------------|-------|
| Fuel | 60–220 cr/unit | 1 hold per unit |
| Organics | 90–350 cr/unit | 1 hold per unit |
| Equipment | 150–600 cr/unit | 2 holds per unit |

> Equipment is bulky - each unit takes **2 cargo holds**, so a 40-hold ship carries only 20 units of equipment vs. 40 units of fuel or organics.

## Port Types & Pricing

Different port archetypes have different price ranges and buy/sell spreads. The spread is the gap between buy price and sell price - it represents the port's margin.

| Port Type | Price Range | Spread | Notes |
|-----------|-------------|--------|-------|
| Standard | Wide | 10% | General trading |
| Fuel Depot / Agri / Mining | Narrow | 6% | Specialty commodity |
| Tech Hub / Research | Wide | 15% | Equipment focus |
| Black Market | Very wide | 22% | Contraband only |
| Pirate Base | Very wide | 20% | Pirate faction |
| Federation Port | Moderate | 8% | Stable, low variance |

**Spread** means the sell price is always `spread%` below the buy price at the same port. A port with a 10% spread buying equipment at 500 cr will sell it for ~450 cr. You make money by buying at one port and selling at another that values the commodity more highly.

## How Prices Are Calculated

Prices use a **logistic curve** based on the port's current stock level:

- When a port is **fully stocked**, prices are at their lowest (supply > demand)
- When a port is **nearly empty**, prices are at their highest (demand > supply)
- Daily **price noise** adds variance (±0.5–1.8% depending on port volatility)

This means prices shift throughout the day as players buy and sell. A port flooded by traders will drop prices; a neglected port will creep higher.

**Volatility levels:**
- **Low:** Prices barely move (stable, predictable)
- **Medium:** Normal variance
- **High:** Significant daily swings (riskier, higher potential reward)

## Buy vs Sell Mechanics

Every port has both a **buy price** (what you pay) and a **sell price** (what you receive). The sell price is always below buy - the port takes a cut. The spread percentage determines how large that cut is.

**Port fee:** A small additional fee applies to all trades (based on transaction size). This is shown in the trade confirmation breakdown.

## Port Availability by Territory

Port type availability varies by territory:

| Territory | Available Port Types |
|-----------|---------------------|
| Federation | Standard, Agri, Depot, Mining, Federation, Research |
| Neutral | Standard, Agri, Depot, Mining, Research |
| Pirate | **Pirate Base, Black Market only** - no regular trading ports |

This is critical for route planning: **you cannot buy or sell standard commodities in pirate space**. Pirate sectors are for contraband and services, not commodity trading.

## Trading Strategy

### Basic Route Trading
1. Find a **producer port** - one that sells your commodity cheap (specialty port, well-stocked)
2. Find a **consumer port** - one that buys expensive (low stock, high demand)
3. Fill your holds at the producer
4. Sell at the consumer
5. Repeat - ideally buying something on the return trip (loop route)

### Maximize Profit Per Turn
- **More holds = more profit per trip** - Cargo Compressors tech upgrade adds 20% capacity
- **Warp drive = more trips** - Cover longer routes in fewer turns
- **Federation ports** are stable but lower margin; **outer rim ports** have more variance but bigger swings
- **Equipment** has the highest price ceiling but costs 2 holds per unit - run the math before loading up

### Example Run

Ship: 40 holds, no upgrades  
Route: Agri port (organics cheap) → Federation Port (organics high demand)

- Buy organics at Agri port: 100 cr/unit × 40 units = 4,000 cr spent
- Sell at Federation Port: 280 cr/unit × 40 units = 11,200 cr received
- **Profit: 7,200 cr** (minus port fee ~1–2%)

Same route with Cargo Compressors (48 holds): **~8,640 cr profit**

## Contraband Trading

Contraband from the Black Market follows different rules. See the [Smuggling guide](/guide/smuggling) for full details on risks, detection, and the Goods Cloaking Device.

Short version: contraband buys cheap in pirate space and sells as the underlying commodity (organics or equipment) at federation ports - with a 75% chance of confiscation if you get scanned.
