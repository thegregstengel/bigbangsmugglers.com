---
title: "Trading & the Market"
date: 2026-08-04
description: "How prices are computed, taxes and fees, cost basis, and routes"
weight: 40
group: trade
tags: [trading]
changed_in: []
stats:
  - { label: "Commodities", value: "3", sub: "fuel, organics, equipment" }
  - { label: "Stock swing", value: "±28%", sub: "off the anchor price" }
  - { label: "Port fee", value: "1%", sub: "both directions" }
---

## The three commodities

| Commodity | Volume per unit |
|---|---|
| Fuel | 1 |
| Organics | 1 |
| Equipment | **2** |

A 200-hold ship carries 200 fuel or 100 equipment. Equipment has the highest
prices in the game and the highest spread, but you move half as many units
per run. That trade-off is the point.

## How a price is actually computed

Every port archetype has an **anchor price** per commodity — the price it
would charge if its shelves were exactly at baseline. Two forces move the
real price off the anchor.

### 1. Stock

Each commodity at each port has three numbers: current **stock**, a
**baseline** it wants to sit at, and a **maximum** capacity. Deviation from
baseline swings the price by up to **±28%**.

```
deviation = (baseline − stock) ÷ baseline                when stock ≤ baseline
          = −(stock − baseline) ÷ (max − baseline)       when stock > baseline
swung     = anchor × (1 + 0.28 × deviation)
```

Bought-out port, stock near zero: deviation near +1, price up to +28%.
Flooded port, stock at maximum: deviation −1, price down to −28%.

The swing applies to **both directions**. A port you flooded charges less
*and pays less*.

### 2. Trade pressure

Pressure accrues **per unit traded** — not per transaction. It multiplies the
buy side and divides the sell side.

```
pressure = 1 + min(1.00, unitsTraded × 0.0001)     capped at ×2.00
buy      = floor(swung × pressure)
sell     = floor(swung ÷ pressure × 0.90)
```

10,000 units through one port is a ×2 buy multiplier: the cap. Pressure
decays by **1,000 units per idle tick**, so a hammered port recovers in a day
or so of being left alone.

Pressure only accrues at **pressure-eligible** archetypes. The Stardock, the
Merchant Exchange, the Pirate Haven, Federation Ports, Pirate Bases and Black
Markets are exempt — you cannot price-shock a starport.

### 3. Restock

Every 4-hour world tick pulls each port's stock back toward its baseline by
`ceil(gap × rate)`:

| Ports | Rate |
|---|---|
| Stardock, Merchant Exchange | 1.00 — snaps all the way home every tick |
| Pirate Haven | 0.50 |
| Everything else | 0.15 |

Scarcity is real, but it is temporary. A port you emptied is roughly 15% of
the way back four hours later.

### The rule nothing can break

After every modifier and every rounding step, **a port's sell price is always
strictly below its buy price** for the same player at the same market state.
Buying and immediately selling at the same port always loses money. No
alignment discount, guild band or configuration can invert it — the engine
clamps the combined buy multiplier to keep the spread positive.

## Taxes and fees

Two charges sit on top of the unit price, both computed on the subtotal.

**Port fee: 1%**, both directions, every port.

**Tax: by archetype.**

| Archetype | Tax |
|---|---|
| Fuel Depot | 1% |
| Stardock, Trading Port, Mining Port | 2% |
| Tech Port | 3% |
| Agricultural Port | 4% |
| Federation Port | 5% — **7%** if you are Pirate-aligned |
| Research Port | 5% |
| Merchant Exchange | **0.5%** |
| Pirate Base, Black Market, Pirate Haven | **0%** |

```
buy total   = subtotal + floor(subtotal × tax) + floor(subtotal × fee)
sell payout = subtotal − floor(subtotal × tax) − floor(subtotal × fee)
```

**Reductions.** The Trader role subtracts up to 2 percentage points from
whatever rate applies, floored at 0. A corporation-held port charges its own
members half rate and everyone else +1pp.

## Cost basis and what "profit" means

Cargo is **pooled**, one stack per commodity. There are no lots to manage,
and there is no cheapest-first ordering.

Each stack carries a **weighted average cost basis** that includes the taxes
and fees you paid on every buy. Buy 50 organics at 80 and 50 more at 120, and
your basis is 100 a unit plus the charges — one number.

Selling never changes the basis of what's left. If you sell 30 of 100 units,
the other 70 keep the same per-unit basis.

When you sell, the game reports `costBasis` (basis × units sold) and
`profit`. **Profit can be negative**, and the game will say so rather than
hiding it. The buy leg's taxes and fees are baked into the basis; whether the
sell leg's charges are netted out depends on the screen — always sanity-check
against your wallet on a large sale.

## Buying and selling

- Each leg costs **1 turn**, regardless of unit count. Move 300 units in one
  transaction, not thirty of ten.
- **Wallet only.** The bank cannot buy cargo.
- Trading **breaks a ship cloak**.
- Trading pays XP: `floor(subtotal ÷ 500)` before weighting.
- Every honest trade leg pays **+1 Merchant Guild standing**.
- The docking gate applies. A hostile alignment can lock you out of a faction
  capital's market entirely, and an outstanding faction warrant is an arrest.
- **Contraband is a separate namespace.** The honest sell action can never
  touch a contraband stack, though contraband still eats your holds. Selling
  it is a different action — see [Smuggling](/guide/smuggling/).

Common refusals: `NOT_AT_PORT`, `NOT_SOLD_HERE` (the port buys it but doesn't
sell it), `INSUFFICIENT_STOCK`, `INSUFFICIENT_HOLDS`, `INSUFFICIENT_CREDITS`,
`PORT_DESTROYED`.

## Where the money is

Anchor prices by archetype. The lowest anchor for a commodity is where you
buy it; the highest is where you sell it. Asterisked entries are **buy-only**
— the port pays you but never sells.

| Archetype | Fuel | Organics | Equipment |
|---|---|---|---|
| Agricultural Port | 160* | **75** | 850* |
| Fuel Depot | **90** | 215* | 600* |
| Research Port | 145* | 185* | **350** |
| Tech Port | 135* | 155* | **375** |
| Black Market | 80 | 100 | 300 |
| Pirate Base / Pirate Haven | 100 | 125 | 500 |
| Mining Port | 105 | **240** | 550 |
| Trading Port | 115 | 135 | 550 |
| Merchant Exchange | 110 | 130 | 520 |
| Stardock | 125 | 150 | 625 |
| Federation Port | **150** | **170** | **750** |

The catalog enforces that the cheapest *lawful* seller of each commodity is a
specialist, not a generalist. That is why the Stardock and the Exchange are
never the cheapest place to buy anything: they win on depth, tax and
convenience.

### The obvious routes

- **Organics: Agricultural → Mining.** Anchor 75 to anchor 240. The widest
  lawful spread in the game, and mining ports sit out in `outer` and
  `outer_rim` where the trip is dangerous. That's the deal.
- **Organics: Agricultural → Federation Port.** 75 to 170, entirely inside
  PvP-free space. Narrower, safer, taxed at 5%.
- **Fuel: Depot → Federation Port.** 90 to 150, and Federation Ports sit deep
  in safe territory.
- **Equipment: Research or Tech → Federation Port or Stardock.** 350 to 750
  is the biggest absolute spread anywhere — but equipment is 2 volume, so per
  hold it's 200 rather than 400.

Underworld ports undercut everyone by design and pay no tax. A Black Market
sells equipment at anchor 300, the cheapest in the galaxy, and charges
nothing to trade there. Getting to one means being in pirate territory, and
getting *back* to a good market means crossing the map with full holds.

### Reading a route properly

The anchor table is a starting point, not an answer. What actually matters:

1. **Live prices, not anchors.** A mining port someone emptied yesterday is
   paying 28% under its anchor. The Merchant Exchange price board shows you
   this for every port you've visited, free.
2. **Pool depth.** An Agricultural Port holds 60,000 organics; a Mining Port
   will only buy into a 2,000-unit pool before its stock deviation starts
   eating your price. You can flood a small port in one run.
3. **Turns per credit.** A 30-hop round trip at 1 turn a hop plus 2 trade
   turns is 32 turns. At the default 250-turn cycle that's eight runs. A
   tighter loop with a worse spread often wins.
4. **Your alignment.** At a faction capital, deep alignment on the right side
   is up to −20% on what you pay. On the wrong side it's up to +50%, plus a
   sell penalty.

## Price modifiers you carry

Two per-player bands ride on top of the market:

**Alignment band** — only at Federation Ports, the Stardock, Pirate Bases and
the Pirate Haven. Linear in your alignment: at +1000 alignment you buy 20%
cheaper at Federation ports; at −1000 you pay 50% more there *and* receive
less when you sell. Mirrored at pirate ports.

**Merchant Guild band** — at **every** port. Buys scale down to −10% as your
guild standing approaches 1,000. Buy-side only; there is no sell-side guild
bonus, because one would break the round-trip rule.

Both are shown in the quote before you commit. Both are clamped so the
combined discount can never invert the spread.

## Two markets that aren't ports

**Trader NPCs deal on the roadside.** A trader contact you don't fight can be
traded with: they sell at **×1.35** of the standard anchor and buy at
**×0.65** — always worse than a real port, priced for convenience, three
deals per trader. Deeper toward the rim they sometimes carry contraband. See
[NPCs & Encounters](/guide/npcs/#trading-with-a-trader).

**Player trading posts sell planet production.** A planet with a trading post
runs a real storefront: visiting captains buy off its shelf at roughly 10%
under the commodity anchor, floored just above whatever the best port in the
same sector would pay — so there is never a same-sector flip, but a post on
your route can genuinely undercut the port next door. The proceeds accrue in
the owner's robbable till. See [Planets](/guide/planets/#trading-posts).

## The price board

The Merchant Exchange runs a **price board**: live prices and stock for every
port in every sector you've visited, sorted nearest-first, up to 200 ports.
Free, no turns, no credits.

It is the single strongest trading tool in the game and it costs nothing but
the trip to the Exchange.
