---
title: "Planets"
date: 2026-08-04
draft: false
description: "Claiming, structures, storage, garrisons, raids and starbases"
weight: 16
toc: true
---

*Accurate as of v2.0.8 (August 2026).*

Planets are the late-game economy: a slow, compounding, defensible income
that runs whether or not you're logged in — and a fixed target other captains
can find.

## Claiming

| | |
|---|---|
| Level gate | **10** |
| Cost | **150,000 cr**, wallet only |
| Turns | 1 |
| Requirements | Be in the sector, planet unowned |
| Truce after claim | 12 hours |

**Alignment gates by territory:**

- In **Federation territory** you need alignment **≥ +100**.
- In **pirate territory** you need alignment **≤ −100**.
- Unincorporated space has no alignment gate.

Claiming in aligned territory pays **±250 alignment** — the single largest
alignment swing available from one action.

A fresh planet starts at population 50, population cap 500, storage cap 2,000
and no structures.

## Structures

Six of them, each maxing at **level 5**. Cost of level *n* is
`floor(baseCost × multiplier^(n−1))`, and building costs 1 turn.

| Structure | Base | Multiplier | Level gate | Per level |
|---|---|---|---|---|
| **Warehouse** | 5,000 | ×1.8 | — | +2,000 storage |
| **Habitat** | 6,000 | ×1.8 | — | +250 population cap, +10% growth |
| **Factory** | 7,500 | ×1.8 | 5 | +15% production |
| **Shield Generator** | 10,000 | ×2.0 | 5 | +15% defense (multiplicative), +12 flat defense |
| **Barracks** | 7,500 | ×1.9 | 12 | +4 garrison fighters per tick |
| **Citadel** | 25,000 | ×2.0 | 18 | +10% production, +10% defense, **×2 garrison cap**, +25 flat defense |

The **Citadel additionally requires Factory and Shield Generator at level 3**.

The ×2.0 multipliers bite. A level-5 Citadel costs 25,000 × 2⁴ = 400,000 on
its own, and the full ladder to Citadel 5 is 775,000 cr.

## Production

Every 4-hour world tick:

```
output = floor(baseRate
              × (1 + 0.15 × factoryLevel)
              × (0.2 + 0.8 × population ÷ populationCap)
              × regionMultiplier
              × (1 + 0.10 × citadelLevel))
```

Base rates: **fuel 35, organics 25, equipment 13** per tick. Region
multiplier is **1.10 in `outer`**, **1.05 in `outer_rim`**, 1.00 everywhere
else.

Read the population term carefully. At zero population you still get 20% of
base; at cap you get 100%. **Population is a 5× multiplier on everything the
planet makes**, and it is the cheapest one to buy.

Population grows per tick by:

```
floor(10 × (1 + 0.10 × habitatLevel)) − floor(population × 1%)
```

At 1,000 population, attrition is 10 a tick — which exactly cancels base
growth. Without Habitat levels, a planet stalls near 1,000. Habitats raise
both the cap and the growth rate.

You can also **colonize**: deploy Mining Workers from your inventory 1:1 into
population, 0 turns, clamped at the cap. Workers cost 300 cr each at any
`recruitment` service. Buying the population is dramatically faster than
growing it.

Production must be **collected** — it accrues until you show up.

## Storage

Base 2,000, +2,000 per Warehouse level, so a maxed Warehouse holds 12,000.
Equipment counts **double** against the cap, exactly as it does in your holds.

Deposits and withdrawals cost **0 turns** and are capped by your holds.

Corp-mates' access is governed by corporation policy: `storage.view` and
`storage.deposit` default **on**, `storage.withdraw` defaults **off**.

## Garrisons

Garrison fighters are the planet's defense.

- Base cap **500**, **doubled per Citadel level** — a Citadel 5 planet caps
  at 16,000.
- Staff it with **Security Personnel** bought at any `recruitment` service
  for 100 cr each, deployed in-sector, 0 turns.
- Barracks add **4 fighters per level per tick** automatically.

## Landing

Landing on **your own or your corporation's** planet grants **landing
protection**: attackers get `TARGET_PROTECTED`. It is the single best place
to sit out a hostile window — better than a defense contract, and free.

It lasts until the planet falls.

## Raids

Level 15 to attack, 1 turn.

```
attackerPower = (fighters × 0.8 × combatAI + shields × 1.2 + torpedoes × 2.0)
                × (1 + siegeBonus)
defenderPower = max(10, garrison × 0.8 × (1 + structureDefense) + structuralDefense)

structureDefense   = (1 + 0.15 × shieldLevel) × (1 + 0.10 × citadelLevel) − 1
structuralDefense  = 12 × shieldLevel + 25 × citadelLevel

winChance = attackerPower ÷ (attackerPower + defenderPower) ± 0.02
```

**Structure defense is multiplicative, not additive.** At Shield 5 and
Citadel 5 that's 1.75 × 1.5 − 1 = **+162.5%**, not the +125% you'd get by
adding them. Fortifying compounds.

The `structuralDefense` term is **garrison-independent** — a Shield 5 /
Citadel 5 planet contributes 185 defense power even with an empty garrison.
Fortresses defend themselves.

**On a win:** garrison drops to 50%, you take **25% of each stored
commodity** (as much as your holds fit) plus **10% of the owner's wallet**
capped at 5,000 cr. Raider-line hulls multiply both.

**On a loss:** garrison drops to 80%, you lose **every fighter**, and you
take `max(shields, 75% of shields + hull)` damage through the hull spill. A
failed raid on a fortified planet will destroy your ship.

Blocked by: your own corporation's planet, an active truce, your own PvP
immunity, or a galaxy with PvP off.

## Capture

Level 15, 1 turn, and **the garrison must be at zero**. Raid until it's
empty, then take it.

Capture transfers **everything** — structures, storage, population,
everything. Any of the old owner's ships parked there are launched. A
24-hour truce protects the new owner.

Corporation-on-corporation capture within the same corp is blocked.

## Starbases

The capstone. **1,500,000 cr**, level **26**, and it requires **every
structure at level 5**. One starbase per player per galaxy.

What it buys:

**Respawn priority.** Owning a starbase and having at least one other ship in
your garage gives you a *choice* when you die: Sector 0, or your starbase's
sector. Without it, you're dropped at Sector 0 and that's that. For anyone
operating in the rim, that is the difference between a 2-turn recovery and a
40-turn crawl back out.

**A vault.** Owner-only storage for credits and items, accessible in-sector,
0 turns. Corp-mates cannot see it, let alone touch it.

**A ship pool.** Corp members can donate ships to a corp starbase (cargo is
deleted on donation) and claim pooled ships into their own garage — arriving
inactive and empty.

**A fleet cargo destination.**

If the starbase falls before you resolve a pod choice, the choice degrades to
Sector 0.

## Trading posts

A trading post turns a planet into passive income: it sells your stored
production automatically and accumulates credits in a till you collect.

Build it, upgrade it, refill it from storage, and collect the till. Exports
pay **30 cr per unit**. Others can **rob** it — which pays them loot and
earns them a bounty.

The full economics — build cost, upgrade cost per level, max level, units
sold per tick per level, price factor — are season configuration and are
shipped to the client on the planet info screen. Read them there rather than
trusting a number on this page.

## Renaming and transferring

**Rename** is owner-only, requires being in the sector, costs 0 turns, runs
through the profanity gate, and posts nothing publicly. 3 to 30 characters.

**Transfer** hands the deed to another member of your corporation. That is
the only ownership transfer in the game that doesn't involve a siege.

## Is it worth it?

A bare claim is 150,000 cr for roughly 15 credits' worth of production a tick.
That's a bad deal on its own.

The compounding case: Habitats to raise population toward the cap (5× on
everything), a Factory ladder (+75% at level 5), Warehouses so the output has
somewhere to go, and a trading post to sell it without you flying there.
Fortification (Shield + Citadel) is what stops another corporation taking the
whole investment in an afternoon.

Half-built planets are the worst outcome in the game: expensive enough to
hurt, productive enough to notice, and defenseless.
