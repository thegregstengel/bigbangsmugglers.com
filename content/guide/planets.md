---
title: "Planets"
date: 2026-07-02
draft: false
description: "Claim and develop planets for passive income and strategic control"
weight: 17
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

Planets are the late-game cornerstone of Big Bang Smugglers. Claim one, develop it with structures, and it generates commodities and passive credit income on every production cycle while you trade, fight, and explore. A developed planet is also a fortress: garrison it, mine its sector, park your ship behind its shields, and — at the very top — crown it with a Starbase.

One thing to internalize early: **planet life runs on the 4-hour cycle**, not a daily one. Production, population growth, trading post refills — all of it ticks every 4 hours at 00:00, 04:00, 08:00, 12:00, 16:00, and 20:00 UTC. That is 6 cycles per day.

## Planet Types

Planets come in four types:

- **Habitable World** — temperate, capable of supporting large populations
- **Resource Planet** — mineral-rich, high production potential
- **Gas Giant** — massive, inhospitable, and visually striking
- **Barren World** — sparse and unforgiving, but claimable

Type is flavor only — all planet types use the same production rates, costs, and caps. Claim whichever one is in the right sector.

## Claiming a Planet

Navigate to a sector with an unclaimed planet, which you will see listed as a point of interest on the Nav screen. Open the planet and tap **Claim Planet**. The planet must be unclaimed and you must be in the same sector.

**Claiming costs 150,000 credits from your wallet — bank credits do not count — plus 1 turn.** Withdraw from the bank first if you need to.

**Alignment gates apply by territory:**

- Federation territory: requires alignment of **+100 or higher**, and claiming grants **+250 alignment**
- Pirate territory: requires alignment of **−100 or lower**, and claiming grants **−250 alignment**
- Unincorporated territory: no gate, no alignment change

A freshly claimed planet starts with population 50, all structures at level 0, and a **12-hour truce** during which it cannot be attacked or captured. Your name appears as the owner and the claim is announced on the galaxy feed. If you belong to a corporation, the planet is tagged with your corp — corp members can collect production, use storage, and land there.

## Population and Workers

Population directly scales production output, from 20% when the planet is empty up to 100% at the population cap. A full planet produces five times what an empty one does.

**Growing population:**

- Buy **Mining Workers** at any Starport (300 cr each, Recruitment) and deploy them from the planet screen. Workers transfer from your inventory to the population 1-for-1, free of turns.
- Population also grows naturally every 4-hour cycle: a base of 10 new colonists, boosted 10% per Habitat level, minus 1% attrition on the existing population. Natural growth stalls out as attrition catches up — topping out a large planet means shipping workers.

**Population cap:** base 500, plus 250 per Habitat level, up to 1,750 at Habitat 5.

## Structures

Six structures, each upgradeable from level 0 to 5. Every upgrade costs **1 turn plus credits from your wallet** (bank credits do not count).

| Structure | Base Cost | Cost Multiplier | Effect per Level |
|-----------|-----------|-----------------|------------------|
| Warehouse | 5,000 cr | 1.8x | +2,000 storage capacity |
| Habitat | 6,000 cr | 1.8x | +250 population cap, +10% population growth |
| Factory | 7,500 cr | 1.8x | +15% production |
| Shield Generator | 10,000 cr | 2.0x | +15% garrison defense, +12 flat defense |
| Barracks | 7,500 cr | 1.9x | +4 free garrison fighters per cycle |
| Citadel | 25,000 cr | 2.0x | +10% production, +10% defense, +25 flat defense, doubles garrison cap |

Each level's cost is the base times the multiplier raised once per level already built:

| Structure | L1 | L2 | L3 | L4 | L5 | Total |
|-----------|-----|-----|-----|-----|-----|-------|
| Warehouse | 5,000 | 9,000 | 16,200 | 29,160 | 52,488 | 111,848 |
| Habitat | 6,000 | 10,800 | 19,440 | 34,992 | 62,985 | 134,217 |
| Factory | 7,500 | 13,500 | 24,300 | 43,740 | 78,732 | 167,772 |
| Shield Generator | 10,000 | 20,000 | 40,000 | 80,000 | 160,000 | 310,000 |
| Barracks | 7,500 | 14,250 | 27,075 | 51,442 | 97,740 | 198,007 |
| Citadel | 25,000 | 50,000 | 100,000 | 200,000 | 400,000 | 775,000 |

Maxing all six structures runs about **1,700,000 cr** on top of the 150,000 cr claim.

**The Citadel is the endgame structure.** Building or upgrading it requires **Factory level 3 and Shield Generator level 3 or higher**. Besides its production and defense bonuses, each Citadel level **doubles the planet's garrison cap**: 500 base, then 1,000 / 2,000 / 4,000 / 8,000 / 16,000 at Citadel 1 through 5.

## Production

Every 4-hour cycle, the planet produces commodities:

```
factoryMultiplier    = 1 + (0.15 × factoryLevel)
populationMultiplier = 0.2 + ((population / populationCap) × 0.8)
citadelMultiplier    = 1 + (0.10 × citadelLevel)

fuel per cycle      = floor(35 × factory × population × citadel)
organics per cycle  = floor(25 × factory × population × citadel)
equipment per cycle = floor(13 × factory × population × citadel)
```

A fully maxed planet — Factory 5, Citadel 5, full population — produces about **91 fuel, 65 organics, and 34 equipment per cycle** (190 units), six times a day.

**Uncollected output is overwritten every cycle.** Production does not accumulate: each new cycle replaces whatever you did not collect from the last one. Collect often — you can bank at most one cycle's worth of resources per cycle.

**Collecting:** tap Collect on the planet's Production tab. Collection is free (0 turns), works from anywhere in the galaxy, and can be done by you or any member of your corporation. Collected commodities go into **planet storage**, not your ship — use Withdraw on the Storage tab to load them into your cargo hold.

Note: some in-app production and export figures currently disagree with what the planet actually produces. The numbers above reflect the real backend output.

## Passive Export Income

On top of commodities, planets pay **passive credit income directly to your bank** every production cycle, whether or not you collect. The planet auto-exports its output at a flat **30 cr per unit produced**.

A maxed planet producing 190 units per cycle banks about 5,700 cr per cycle — roughly **34,000 cr per day** — with zero effort. Because it goes to the bank, not your wallet, export income is safe from raiders.

## Planet Storage

Planet storage holds collected production and anything you deposit. Capacity is **2,000 units base, plus 2,000 per Warehouse level** (12,000 at Warehouse 5). Equipment takes 2 units of storage space; fuel and organics take 1.

**Deposit and Withdraw** move cargo between your ship and planet storage. Both are free (0 turns), require your ship to be in the planet's sector, and are available to you and your corp members. If storage is nearly full, collection is scaled down to fit — keep it drained.

## Garrison

The garrison is your planet's standing defense force. Buy **Security Personnel** at any Starport (500 cr each, Recruitment) and deploy them from the Garrison card on the planet's Overview tab. Garrison units move from your player inventory — they are a separate pool from your ship's combat fighters. The Barracks adds 4 free garrison fighters per level every cycle.

**Garrison cap:** 500, doubled by each Citadel level (up to 16,000 at Citadel 5).

The garrison defends against **planet sieges only** — it does not join ship combat in the sector. If you want automated defense that fires on hostile ships entering the sector, push garrison fighters out as sector defense from the planet screen — see [Deployables](/guide/deployables/) for how deployed fighters, mines, and the rest of the sector defense stack work.

## Defense and Sieges

Other players can raid your planet (PvP-enabled galaxies only, and never during a truce). Attacking costs the raider 1 turn.

The defense is a single power formula fed by three things: **garrison size**, boosted 15% per Shield Generator level and 10% per Citadel level, plus **flat structural defense** of 12 per Shield level and 25 per Citadel level. The attacker's power comes from their fighters, shields, and torpedoes.

**If the attacker wins:**

- They steal 25% of each stored commodity (limited by their free cargo holds)
- They steal 10% of your **wallet** credits, capped at 5,000 — bank credits are never touched
- Your garrison is cut in half

**If the attacker loses, it is catastrophic for them:** their ship is disabled and **all of their fighters and shields are wiped out**. Your garrison drops 20%.

**Capture:** once a planet's garrison hits **exactly 0**, an attacker in the sector can capture it outright for 1 turn. Everything transfers — structures, storage, population, any Trading Post, even a Starbase — as spoils of war. Capture starts a **24-hour truce** protecting the new owner.

The defensive loop is simple: keep the garrison topped up so raids stay expensive, and never let it hit zero.

## Planet Parking

You can **land your ship on your own planet** (or a corp member's) from the Ship Landing card on the planet screen. Landing and launching are free.

A landed ship is **hidden from sector target lists and cannot be attacked** while the planet stands — attackers must defeat the planet first. It is the safest place to log off in hostile space, as long as the planet holds. Moving or warping launches your ship automatically.

## Renaming

The owner can rename a planet for free from the planet screen. If the planet has a Trading Post, its port name updates to match.

## Trading Posts

A Trading Post is a player-built port that lets other captains buy commodities from your planet. It is a late-game investment — expensive to build, but it generates passive income while you do other things.

### Building a Trading Post

You need two things before you can build:

- Warehouse Level 2 on the planet
- 100,000 credits in your wallet or bank

Open your planet screen, go to the **Trading Post** tab, and tap Build Trading Post. The cost comes from your wallet first, then your bank if the wallet falls short. The post is permanent and cannot be demolished.

### How It Works

Once built, the post appears in your sector as a named port on the Nav screen — other players will see it as "**{Planet} Trading Exchange ({your name})**". Any player who enters the sector can open it and buy commodities. The post is buy-only — players cannot sell to it.

Stock transfers free of charge from your planet storage to the post every 4 hours at the same boundaries as turn resets. You can also trigger a free manual refill from the Trading Post tab once per 4-hour window. If your planet storage is empty, the post runs dry until production refills it.

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

The "% below standard" discount applies to the **top of the price band** — the ceiling is lowered, the floor stays put, and actual quotes land in between. The total investment to reach Level 5 is 1,700,000 cr and 160,000 XP. A max-level post running at full stock is a significant passive income source.

### Defending Against Robbery

Pirate-aligned captains (alignment of −500 or lower) in your sector can attempt to rob your Trading Post. Each robber gets **one attempt per post per 4-hour window**.

Their base success chance is 40%. A Goods Cloaking Device adds 15% to their odds and is consumed on the attempt. **Your defense is the planet garrison**: each tier of 100 garrison fighters cuts their chance by 5%, up to 5 tiers — so 500+ garrison drops an uncloaked robber to 15%. Success is clamped between 10% and 75% regardless of modifiers.

A successful robbery steals up to 30% of the post's **current stock** per commodity. Only stock sitting in the post is at risk — planet storage and your bank are never touched, so keeping stock lean between shopper visits limits your exposure.

Every attempt — success or failure — triggers a galaxy-wide feed announcement naming the attacker and your post, and you get a private alert. Failed attempts are still visible to everyone and a natural reason for other players to post a bounty on the attacker.

## Starbases

The Starbase is the capstone of planet development. Requirements:

- **All six structures at level 5** on the planet
- **1,500,000 credits in your wallet** — wallet only, no bank fallback
- **One Starbase per player** — grow your corporation to command more

A Starbase never appears on the Nav map and cannot be attacked or destroyed. It lives on the planet's Structures tab, and it changes hands intact if the planet is captured.

**What it gives you:**

- **Credit and item vault** — unlimited storage for credits and inventory items (workers, fighters, beacons, mines, cloaking devices). Owner-only, and you must be in the planet's sector to use it.
- **Hangar** — store and switch ships at the planet without flying to a starport. Ships cannot be sold here.
- **Escape-pod respawn point** — if your ship is destroyed, your escape pod returns to your Starbase sector instead of Sector 0.
- **Corp infrastructure** — if the planet belongs to your corporation, the Starbase becomes the corp's shared ship pool and the landing dock for fleet combat loot. See [Corporations & Fleets](/guide/corporations-fleets/).

## Strategic Notes

- Collect every cycle you can. Uncollected production is overwritten, not banked.
- Prioritize workers before factories. The population multiplier has a bigger impact at low population than additional Factory levels.
- Deploy proximity mines and sector-defense fighters in your planet's sector as the first line of defense before a siege ever starts. See [Deployables](/guide/deployables/).
- Rush Factory 3 and Shield 3 to unlock the Citadel — its garrison-cap doubling is what makes a planet genuinely hard to take.
- Planets in pirate space are more exposed to attacks but carry no contraband enforcement risk.
- Never let the garrison hit 0 — that is the only condition under which your planet can be captured.
