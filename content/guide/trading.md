---
title: "Trading & Economy"
date: 2026-07-02
draft: false
description: "Master the art of profitable trading"
weight: 4
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

Trading is the backbone of your career. The market is simpler than it looks: every port type charges a fixed price for each commodity, and profit comes from hauling goods between port types that value them differently. Learn the price table, mind the fees, and maximize your credits per turn.

## The Three Commodities

| Commodity | Buy Price (by port type) | Notes |
|-----------|--------------------------|-------|
| Fuel | 60 to 130 cr/unit | 1 hold per unit |
| Organics | 60 to 200 cr/unit | 1 hold per unit |
| Equipment | 200 to 700 cr/unit | 2 holds per unit |

Equipment is bulky. Each unit takes 2 cargo holds, so a 40-hold ship carries only 20 units of equipment versus 40 units of fuel or organics.

## Port Types & Prices

Each port type has a fixed base price for each commodity, identical in every galaxy. Stock level does **not** move prices — a nearly empty port charges the same as a full one. The two things that do move prices are trade pressure and your reputation (see below).

Buy prices by port type:

| Port Type | Fuel | Organics | Equipment |
|-----------|------|----------|-----------|
| Stardock | 100 | 120 | 500 |
| Federation Port | 120 | 140 | 600 |
| Standard Port | 90 | 110 | 450 |
| Fuel Depot | 70 | 180 | 500 |
| Agricultural Station | 130 | 60 | 700 |
| Tech Outpost | 110 | 130 | 300 |
| Pirate Base | 80 | 100 | 400 |
| Black Market | 60 | 80 | 200 |
| Mining Station | 85 | 200 | 450 |
| Research Complex | 120 | 150 | 280 |

The **sell price is 90% of the buy price** at the same port. Selling back where you bought loses that 10% plus taxes and fees on both legs — always haul to a port type with a higher base price instead.

Every port type trades all three commodities. Yes, including Pirate Bases and Black Markets — in fact the Black Market is the cheapest source of fuel and equipment in the game. The catch: anything you buy at a Black Market port is silently flagged as contraband (Pirate Base purchases are not flagged). See [Smuggling](/guide/smuggling/) before you load up.

## What Actually Moves Prices

### Trade pressure

Standard-economy ports (Standard, Fuel Depot, Agricultural, Tech, Mining, Research) track per-commodity trade pressure. Federation, Stardock, Pirate, and Black Market ports never accumulate it.

- Every buy **transaction** adds 1 point of buy pressure to that commodity; every sell adds 1 point of sell pressure. Points count transactions, not units — one big trade is gentler on the market than many small ones.
- Each point moves the price about **0.2%**: buy pressure pushes the buy price up (no ceiling), sell pressure pushes the sell price down (floored at 1 cr).
- Pressure recovers **20 points per 4-hour cycle**, but only for commodities that saw zero trades during that cycle. Hammering the same port erodes your margin, and the port needs quiet cycles to recover.

The ▲/▼ percentages on the trade screen show current pressure adjustments.

### Reputation

Your standing moves prices more than anything else. At Federation and Pirate ports, faction alignment swings buy prices from **20% off** (friendly) to **50% markup** (hostile). Trader reputation adds up to ±10% at every port. Sell prices move in the opposite direction — friendly factions also pay you more when you sell. See [Reputation & Factions](/guide/reputation-factions/) for the full ladders.

## Fees & Taxes

Every trade pays a flat **1% port fee** plus a port-type tax:

| Port Type | Tax |
|-----------|-----|
| Federation Port | 5% (7% if you're Pirate faction) |
| Tech Outpost | 3% |
| Everything else | 2% |

So a typical leg costs about 3% in overhead, and Federation ports cost 6–8%. The fee estimate shown in the sell dialog is a flat guess — the actual charge uses the real per-port rates above.

## Port Availability by Territory

| Territory | Port Types You'll Find |
|-----------|------------------------|
| Federation | Everything except Pirate Bases and Black Markets (the Stardock is always at Sector 0) |
| Unincorporated | Everything except Black Markets — including Federation Ports and Pirate Bases |
| Pirate | Pirate Bases and Black Markets only |

You **can** buy and sell standard commodities in pirate space — Pirate Bases and Black Markets trade all three commodities at the prices in the table above.

## Trading Strategy

### Basic Route

1. Pick a commodity and find the port type with the lowest base price
2. Find a port type with a high base price for the same commodity
3. Fill your holds at the cheap port
4. Haul and sell at the expensive one
5. Buy something for the return leg if the ports line up

The flagship route: **organics from an Agricultural Station (60 cr) to a Mining Station (sells at 180 cr)**. Other strong pairs are fuel from a Fuel Depot (70) to a Federation Port, and equipment from a Research Complex to an Agricultural Station. Black Market fuel and equipment are cheaper still — but everything bought there is flagged contraband, and Federation Ports are exactly where customs scans happen. Route Black Market goods to neutral ports, and read [Smuggling](/guide/smuggling/) first.

### Example Run

Ship with 40 holds, Agricultural Station to Mining Station:

- Buy 40 organics at 60 cr/unit = 2,400 cr, plus 2% tax and 1% fee = **2,472 cr spent**
- Sell at the Mining Station for 180 cr/unit = 7,200 cr, minus 2% tax and 1% fee = **6,984 cr received**
- **Profit: about 4,500 cr** — roughly 113 cr per hold

With Cargo Compressors installed (48 holds): about 5,400 cr on the same route.

Numbers assume neutral reputation and no trade pressure; your actual results shift with both.

### Maximize Profit Per Turn

More holds means more profit per trip. The Cargo Compressors tech upgrade adds 20% capacity permanently (see [Tech Upgrades](/guide/tech-upgrades/)). A warp drive lets you cover longer routes in fewer turns. Spread your trading across multiple ports rather than grinding one — trade pressure punishes repeat business.

Equipment has the highest prices but costs 2 holds per unit. Run the math before committing your entire hold to equipment.

## Port Stock Is Finite

Ports never restock commodities. When you buy out a port's supply of something, it stays bought out until other players sell that commodity back to it. Popular routes near spawn areas can genuinely run dry over a season.

The exception is player-built **Trading Posts**, which refill from their planet's storage every 4-hour cycle. See [Planets](/guide/planets/).

## Turns, Lots, and Cost Tracking

Every buy or sell is **1 turn per transaction**. Every purchase creates a separate cargo lot stored with its own cost basis. If you buy 10 equipment at 280 cr and later buy 10 more at 450 cr, you have two lots in your hold.

When you sell, the game shows the breakdown before you confirm:

```
Sell 20 Equipment @ 405 cr?

Lots:
  10 @ 200 cr/unit (cost basis)
  10 @ 450 cr/unit (cost basis)

Avg Cost:    325 cr/unit
Subtotal:    8,100 cr
Est. Fees:   ~243 cr
Est. Total:  ~7,857 cr
Est. Profit: +1,357 cr
```

Lots sell **contraband first, then cheapest cost basis first** (not oldest first). If you sell a partial quantity, the cheapest lot is consumed first — selling 15 of those 20 units takes all 10 from the 200 cr lot and 5 from the 450 cr lot.

Two things to know about multi-lot sales:

- Each lot is its own transaction — selling across 3 lots costs **3 turns** and pays 3 sets of tax and fees.
- The profit figure shown after the sale is sale price minus cost basis. It does not subtract the taxes and fees you paid on either leg, so it slightly overstates your true profit.

### Max Buttons

**Buy Max** fills to the smaller of your free holds or the port's stock — it does **not** check your credits, so Max can propose a buy you can't afford (the trade is then rejected). **Sell Max** sells every unit of that commodity across all your lots.

## Wallet vs Bank

Trades pay from your **wallet** only. Combat loot also comes only from your wallet — banked credits can never be stolen in a fight. Deposits and withdrawals are free, unlimited, and cost no turns. The Banking service appears at Stardock and Federation ports and at every Starport.

Rule of thumb: bank your profits before flying anywhere dangerous.

## Contraband Lots

Contraband is stored as separate lots from regular cargo of the same type. If you buy normal equipment and then Stolen Equipment on the Black Market, your hold shows two distinct groups:

```
⚙️ Equipment      10 units   avg 450 cr
⚙️ Equipment 🔴   10 units   avg 40 cr    Contraband
```

Contraband lots are highlighted in red, marked "sells first," and always sell before regular lots regardless of price — minimizing your time carrying hot cargo.

Two detection systems apply:

- **Federation customs** scan you when you **open the trade screen** at a Federation port (not on arrival), on a 30-minute cooldown. If you're caught, *all* your contraband in the galaxy is seized, you pay a fine of 10% of its value (capped at your wallet), and you lose 5 alignment.
- **Sale-time checks** can block a contraband sale outright — the sale simply fails with no penalty or turn cost, and you can retry.

See the [Smuggling guide](/guide/smuggling/) for detection rates, cloaking devices, and how to run contraband profitably.
