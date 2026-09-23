---
title: "Progression"
date: 2026-08-04
description: "XP, levels, gates, roles, insignia, prestige and leaderboards"
weight: 18
group: compete
tags: [progression]
changed_in: [2.0.8]
---

## The level curve

```
level = floor(sqrt(XP ÷ divisor)) + 1        capped at the season's max level
XP for level n = (n − 1)² × divisor
```

**The ladder is pinned per season.** The curve's divisor and level cap are
set when a season's galaxy is created and never move mid-season. Seasons
created before the ladder migration run a 50-level ladder; every newer
season runs a **100-level ladder** whose divisor is tuned to its length, so
each unlock lands at the same *fraction* of the season whether it's a 30-day
sprint or a long grind. Same content spine, different pace.

Because the numbers differ season to season, this guide describes gates by
**depth in the ladder**, not by level number. The in-game unlock list always
shows your season's exact levels and XP totals.

The curve is deliberately calibrated to a season: the reference ladder is
validated against a play rate of **4,500 XP a day over 12 weeks**. A season
that shipped a top gate you couldn't reach in the time available wouldn't
load.

## Where XP comes from

| Source | What it pays |
|---|---|
| **Exploration** | 10 per new sector, +25 for a port, +50 for a planet, **+100 for a landmark** |
| **Trade** | `floor(subtotal ÷ 500)` per leg |
| **Combat** | Scaled by how close the fight was and both hull tiers, 50–450 for the winner |
| **Missions** | 200–5,000 per event |
| **Planets** | `60 × weight × level reached` per structure level (60–900), 1 per Mining Worker colonized — see [Planets](/guide/planets/) |
| **Goals** | 100–2,000 per tier |
| **Streaks** | 50–1,000 per milestone |

**Losing a fight pays no XP.** That changed in v2.0.8.

Every source runs through one award path with a per-source weight (all 1.0
today) and an optional season multiplier. There is no XP loss mechanic.

## The unlock ladder, in order

The *order* of unlocks is fixed doctrine; the level numbers belong to your
season. Roughly by depth:

| Depth in the ladder | Unlocks |
|---|---|
| First sessions | Post a bounty; buy contraband |
| Early | **Tier 2 hulls**; Factory and Shield Generator; found a corporation; first retinue tier |
| Early-mid | Sell contraband |
| About a fifth up | **Claim a planet**; join a fleet |
| About a quarter up | **Tier 3 hulls**; Barracks |
| Just under a third | Siege a port; **raid or capture a planet**; lead a fleet |
| About a third | Citadel |
| Past two-fifths | **Tier 4 hulls** |
| Past the midpoint | Build a starbase |
| About two-thirds | **Tier 5 hulls** |
| **The top of the ladder** | **Tesseract drive** |

Whether a given season's ladder *reaches* the last rungs depends on its
tuning — the older 50-level seasons cap out below the Tesseract's gate, so
it never unlocks there. Check the unlock list in game for your season.

Ship tiers and drives also quote an **XP total** beside the level. The two
are one gate expressed two ways — both are derived from the season's own
curve and always agree.

Anything not in this table is ungated at level 1 — the gate table fails open
by design.

## Level ranks

Cosmetic titles derived from level. These thresholds are fixed in code, not
per-season — so on a longer ladder you simply keep the top rank longer:

| Level | Rank |
|---|---|
| 1 | Recruit |
| 3 | Cadet |
| 6 | Pilot |
| 10 | Ensign |
| 15 | Lieutenant |
| 21 | Commander |
| 28 | Captain |
| 36 | Fleet Commander |
| 45 | Admiral |

## Roles

Four specializations. **You do not choose them** — they are pure functions of
your season statistics, recomputed live, with no storage and no reset.

| Role | Driven by | Thresholds (T1–T5) | Perk | Cap |
|---|---|---|---|---|
| **Trader** | Trade legs completed | 15 / 40 / 90 / 175 / 300 | −0.4pp port tax per tier | −2pp |
| **Smuggler** | **Contraband units sold** | 25 / 75 / 180 / 350 / 600 | −2pp customs scan chance per tier | −8pp |
| **Fighter** | Kills | 4 / 12 / 30 / 60 / 110 | +1% combat power per tier | +5% |
| **Explorer** | Sectors explored | 20 / 60 / 140 / 280 / 500 | −1/−1/−2/−2/−3 warp turns | −3 |

You hold all four simultaneously at whatever tier your stats earn. There is
no trade-off and nothing to spend.

The Smuggler branch is worth calling out: in 1.x it derived from criminal
*alignment*, which rewarded murder rather than smuggling. It now derives from
**contraband volume sold**. Killing people does not make you a smuggler.

Each perk applies at exactly one place in the game: Trader at the port tax
calculation, Smuggler at the customs scan roll, Fighter in the combat
resolver's multipliers, Explorer at the warp turn cost — never the Tesseract.

Roles are **season-scoped** and die with the season.

## Insignia

Earn-only cosmetic flex, stored per galaxy, and they **burn with the season**.
They are never purchasable and never stocked in any shop.

Each occupies a render slot on a public surface — the point is that other
players read them on your name.

| Insignia | Slot | Earned by |
|---|---|---|
| **Void-Scarred** | Ship prefix | Survive a fight — win or loss — ending below 10% hull |
| **«Name»'s Bane** | Ship prefix | Kill a named NPC. **First killer only**, one per NPC per season |
| **Hull Whisperer** | Ship prefix | Bestowed by the GM desk on players whose bug reports shaped the season |
| **the Kessel Runner** | Epithet | Gold tier of the Wayfarer goal |
| **Merchant Prince** | Epithet | Gold tier of the trade-legs goal |
| **Dread Captain** | Epithet | Gold tier of the Duelist goal |
| **Shadow Broker** | Epithet | Gold tier of the Shadow Trader goal |
| **Cartographer's Mark** | Sector name | GM grant. Spend it to name one sector you've visited — consumed on use |
| **Corsair Sigil** ☠ | Beacon mark | GM-event exclusive. Your beacons carry the sigil |
| **Honored Arrival** | Fanfare | GM-event exclusive. Starport docks announce your arrival on the feed |
| **Imperial Charter** | Post title | GM-event exclusive. Your trading post renders under Imperial Charter |

An epithet renders as `Handle, the Kessel Runner`. A ship prefix renders as
`⚔ Void-Scarred Wandering Star`.

Insignia are deliberately the **opposite** doctrine to prestige titles: they
are seasonal and they die.

## Prestige

Prestige is the cross-season layer, and it is **strictly cosmetic**. No
title, tier, award or rank has ever fed a ship stat, a credit amount, a turn
count, a combat roll, a price or a standing. Every season starts mechanically
identical for everyone. That is a doctrine with a test walking every read
site, not an intention.

### Lifetime titles

Nineteen of them, earned against account-lifetime statistics.

| Title | Requirement |
|---|---|
| Millionaire / Multimillionaire / Billionaire | 1M / 10M / 1B credits earned |
| Gunner / Centurion / Deadeye | 25 / 100 / 500 kills |
| Duelist / Gladiator | 10 / 50 PvP wins |
| Wayfarer / Cartographer | 1,000 / 5,000 sectors explored |
| Trader / Merchant Prince | 500 / 2,500 trades |
| Contractor / Taskmaster | 50 / 250 missions |
| Headhunter / Manhunter | 10 / 50 bounties |
| Decorated / Distinguished / Hall of Famer | 3 / 8 / 15 season awards |

### Prestige tiers

Derived from how many titles you hold:

| Titles | Tier |
|---|---|
| 0 | 🌑 Drifter |
| 1 | 🌘 Spacer |
| 3 | 🌗 Voyager |
| 6 | 🌖 Veteran |
| 9 | 🌕 Ace |
| 12 | ⭐ Legend |
| 15 | 🌟 Mythic |

## Leaderboards

Nine boards, computed live from season statistics, showing active players in
your galaxy.

| Board | Ranks by |
|---|---|
| **Overall** | XP (credits earned as the tiebreak) |
| Combat | Kills |
| Trade | Trade legs completed |
| Explorer | Sectors explored |
| Missions | Missions completed |
| **Bounty Hunter** | **Bounty credits earned** — payouts at the kill plus redeemed claims — heads as the secondary score |
| **Most Wanted** | Total active bounty money on your head |
| Smuggler | Contraband units sold |
| Corps | Aggregated corporation scores |

**Overall is XP, not credits.** Wealth is not the season metric and never
was.

Leaderboards no longer expose exact player balances — that changed in
v2.0.8.

## Public profiles

Anyone can look you up. A public profile shows your prestige tier and
lifetime titles (cross-season), your season role tiers, your season insignia
(which burn with the galaxy), kills and deaths, and how many seasons you've
played.

It does not show your balances, your location or your cargo.
