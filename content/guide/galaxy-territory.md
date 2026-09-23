---
title: "The Galaxy & Territory"
date: 2026-08-04
description: "Regions, territory, the three starports, and where PvP is legal"
weight: 4
group: fly
tags: [navigation, factions]
changed_in: []
---

## How a galaxy is built

Every season generates a brand-new galaxy from a seed, in seven deterministic
passes: topology, ports, planets, hazards, wormholes, named NPCs, landmarks.
Nothing is hand-placed and nothing repeats between seasons.

Sector count is **free-form per season** — the default is 500, the admissible
range is 20 to 65,536. The old game's four fixed sizes are gone.

Default densities: **15%** of sectors have a port, **10%** a planet, **6%** a
hazard. Three landmarks and twelve named NPCs per galaxy — five pirates,
five Federation officers, and two merchant princes.

## Regions

Six region bands, by distance from Sector 0 as a fraction of the map radius:

| Region | Distance | Character |
|---|---|---|
| `fed_core` | < 0.08 | The Stardock's neighborhood. Patrols everywhere, no pirates, no PvP. |
| `fed_space` | < 0.20 | Federation border. Heavy patrol presence, still no PvP. |
| `inner` | < 0.40 | The commercial belt. Patrols thin out, pirates start appearing. |
| `middle` | < 0.65 | The Merchant Exchange sits here. Balanced risk. |
| `outer` | < 0.85 | Pirate country. Mining and depots. |
| `outer_rim` | ≥ 0.85 | The edge. Maximum pirate density, no patrols at all. |

Region drives NPC spawn rates, smuggling heat and sale detection, planet
production bonuses (+10% in `outer`, +5% in `outer_rim`), and which port
archetypes can generate where.

## Territory

Territory is a separate axis from region, and it is what the law cares about.

**Federation territory** is every sector in `fed_core` and `fed_space`.

**Pirate territory** is the **outermost 8% of sectors by true distance**,
forming one contiguous band. Not scattered pockets — a continuous annulus you
can see on the map.

**Unincorporated** is everything else.

## Where PvP is legal

PvP is blocked in **Federation territory** and in any explicitly flagged safe
zone (Sector 0 is one). That block is absolute — it overrides a galaxy's
PvP-enabled flag.

Everywhere else — unincorporated space and pirate territory — PvP is on,
assuming the season enabled it.

There are three further reasons an attack bounces off a legal target:

- The target is under **PvP immunity** (post-loss, purchased contract, or
  post-death).
- The target is in **your corporation**.
- The target is **landed on their own or their corp's planet**.

## The three starports

Exactly one of each per galaxy, all three permanently uncapturable.

### The Stardock — Sector 0

The Federation capital and the deepest market in the galaxy: million-unit
pools in all three commodities that restock **fully every tick**. Anchors are
mid-range (125 / 150 / 625) — the Stardock wins on depth and convenience, not
on price.

Services: trading, banking, shipyard, tavern, repair, recruitment, defense,
supplies. Tax 2%.

Stocks the **Federation hull line** plus the neutral spine.

**Docking gate:** denies any captain with alignment below **−300**.

### The Pirate Haven

Placed at the geometric center of the pirate band. Deep pools (60k / 50k /
100k) restocking at 0.5 per tick, cheap anchors (100 / 125 / 500), and
**zero tax**.

Services: trading, banking, shipyard, repair, upgrade, blackmarket,
recruitment, supplies. It deliberately does **not** sell defense contracts —
the Haven does not sell law.

Stocks the **Pirate hull line** plus the neutral spine.

**Docking gate:** denies any captain with alignment above **+300**.

### The Merchant Exchange

Placed in the middle band, as far from both other starports as the map
allows. The deepest pools in the galaxy — **two million units** of everything
— restocking fully every tick, and the **lowest lawful tax anywhere at
0.5%**.

Services: trading, banking, shipyard, repair, upgrade, recruitment, supplies,
priceboard, defense. No bounty office, no black market, no customs.

Its unique service is the **price board**: live prices and stock for every
port in every sector you have visited, nearest first, up to 200 ports, for
free and for no turns. If you trade seriously, this is the most valuable
building in the galaxy.

Stocks the **neutral spine only** — no faction hulls at all.

**Docking gate:** none. The Exchange is open to every alignment, which makes
it the one full-service port a Scourge and a Paragon can both walk into.

## Ordinary ports by territory

Which archetypes can generate where:

| Territory / region | Archetypes |
|---|---|
| Pirate territory | Pirate Base, Black Market — nothing else |
| `fed_core`, `fed_space` | Federation Port, Trading Port, Tech Port, Research Port |
| `inner` | Trading Port, Agricultural, Tech, Fuel Depot |
| `middle` | Trading Port, Agricultural, Fuel Depot, Mining |
| `outer` | Mining, Fuel Depot, Trading Port, Pirate Base |
| `outer_rim` | Mining, Pirate Base, Fuel Depot |

Black Markets **only** exist inside pirate territory. Pirate Bases also appear
in unincorporated `outer` and `outer_rim` space.

See [Ports & Services](/guide/starports/) for what each one stocks and buys.

## Landmarks

Three unique named sites per galaxy, generated out past the inner ring: The
Silent Armada, Precursor Ruins, The Crystal Garden, The Cinder, The
Wanderer's Monolith.

Each has a **shared 50,000 cr loot budget** that depletes for the entire
galaxy, and a **24-hour per-player cooldown**. First visit pays **100
exploration XP**.

## Wormholes

Two core–rim bridges plus three random wormholes per galaxy by default, about
30% of them unstable. A stable transit is the only travel in the game that
bypasses mines and hazards. See [Navigation](/guide/navigation/#wormholes).

## No-deploy zones

No ordnance may be deployed — no mines, drones, turrets, buoys or cloak
fields — anywhere in `fed_core` or `fed_space`. Limpet trackers obey the same
placement rules.
