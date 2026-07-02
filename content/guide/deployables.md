---
title: "Deployables"
date: 2026-07-02
draft: false
description: "Beacons, mines, limpet trackers, and sector defense — persistent presence beyond your ship"
weight: 11
toc: true
aliases: ["/guide/beacons-mines/"]
---

*Accurate as of v1.22.0 (July 2026).*

Deployables give you persistent presence in the galaxy beyond your ship. There are four families: **Navigation Beacons** mark sectors you want to find again, **Proximity Mines** damage hostile ships entering sectors you control, **Limpet Trackers** latch onto passing ships and report their location, and **deployed sector-defense fighters** from your planet garrison automatically engage intruders.

## Getting Inventory

Beacons, mines, and limpets are purchased at any Starport's Supply place — "CoreStar Tactical Supply" at Federation ports, "Black Market Supply" at pirate havens.

| Item | Base Price |
|------|------------|
| Navigation Beacon | 2,500 cr |
| Proximity Mine | 5,000 cr |
| Limpet Tracker | 4,000 cr |

Prices are bases — the amount actually charged is adjusted by your faction alignment and trader reputation, from a healthy discount for friends of the house to a steep markup for enemies.

## Deploying: the Bridge Tab

Beacons, mines, and limpets all deploy from one place: **Ship screen → Bridge tab**, in the sector your ship currently occupies (sector-defense fighters deploy from your planet's screen instead). Deploying costs no turns, but a few rules apply to all deployables:

- **Deploying a beacon, mine, or limpet breaks your ship cloak.** Buying does not, and neither does deploying planet defenses.
- **Your own deployables never harm you** — but **corp-mates are NOT immune**. Your mines hit them, your defenses shoot them, and your limpets latch onto them.
- Freshly respawned players with PvP immunity are immune to all hostile deployables until it expires.
- NPCs never trigger deployables — these are player-versus-player tools.

## Navigation Beacons

Beacons are persistent markers you place in sectors you have visited. They appear in the Beacons section of the Nav screen, visible from anywhere in the galaxy, showing your chosen name, the sector number, territory type, and points-of-interest count.

### Deploying a Beacon

1. Navigate to the sector you want to mark
2. Open the Ship screen and go to the **Bridge** tab
3. Tap Deploy Beacon in the Navigation Beacons card
4. Give it a name, up to 15 characters
5. Confirm to place it

Deploying costs 1 beacon from inventory and no turns.

**Limits:** maximum 5 beacons per galaxy at any time, and only one per sector. Other players can beacon the same sector — and can see your beacon when they are in it.

### Warping to a Beacon

The real payoff: if your ship has a warp drive, each of your beacons on the Nav screen has a **Warp** button that jumps you straight there. Normal warp turn costs and interruption rules apply. Beacon your trade hubs, your planets, and your favorite hunting grounds.

### Recalling a Beacon

Tap **Recall (free)** on any of your beacons in the Beacons section. The beacon is removed and **returned to your inventory** for redeployment — beacons are the only deployable you get back.

One naming note: player navigation beacons are not the same thing as the "beacon" landmark some sectors contain. That is a galaxy feature you activate to reveal adjacent sectors — different system, same word.

## Proximity Mines

Mines are perimeter defense for your territory: **you can only deploy them in sectors where you own a planet**. They trigger automatically when hostile ships enter the sector — by move or by warp.

### Deploying Mines

1. Navigate to a sector where you own a planet
2. Open the Ship screen and go to the **Bridge** tab
3. Set a quantity on the Proximity Mines card — you can deploy up to 100 in one action
4. Confirm to place them

### How Mines Trigger

When a hostile ship enters the sector, the number of mines that detonate is fixed by your minefield's size: **the lesser of 3, or 60% of your mine count rounded down**.

| Mines in field | Mines that trigger |
|----------------|--------------------|
| 1 | 0 — never fires |
| 2–3 | 1 |
| 4 | 2 |
| 5+ | 3 (maximum) |

**A single mine never triggers.** Two mines is the minimum effective field; five gives you the full 3-mine detonation on every transit. Beyond five, extra mines add staying power, not damage.

Each trigger deals 30–50 damage **to shields only** — mines never destroy fighters — for a maximum of 150 damage per transit. A ship whose shields hit 0 while it has no fighters left is disabled on the spot. Triggered mines are consumed; the rest stay armed indefinitely.

You get a feed and push notification every time your mines detonate on someone, and the **"Mines you've deployed"** list on the Bridge tab shows every sector where you have mines and how many remain. No need to fly back and check.

### No Counterplay (Yet)

Honesty time: **there is currently no way for a victim to sweep or remove deployed mines**. They cannot be scanned reliably at small counts, cannot be attacked, and never decay. The only way through a minefield is to eat the damage — at most 150 shield damage per pass. Plan your shields accordingly, and if you are the mine owner, enjoy it while it lasts.

Do not confuse player mines with the environmental **minefield hazard** some sectors have — that one is permanent scenery with no owner, a 40% chance of 40–60 damage when you move through (warping in skips it).

## Limpet Trackers

Limpets are intelligence weapons. Plant one in a sector from the Bridge tab and it waits, invisible, until **the first hostile ship passes through — then it latches on and rides along**, reporting that ship's location to you every time it moves or warps. Limpets deal no damage; their payload is information.

### Planting and Tracking

- Plant from the **Bridge tab** in your current sector — no planet ownership required, no turn cost.
- **Cap: 10 active limpets** per galaxy, counting both planted (waiting) and attached (tracking).
- A planted limpet waits indefinitely. Once attached, a tracker lasts **48 hours** before falling off.
- The latch is silent — the target gets no notification. You get a feed and push alert the moment it attaches.
- Your live tracking list is on the Bridge tab's Limpet Trackers card: each attached tracker shows the target pilot, ship class, and last-known sector; planted limpets show where they are waiting.
- **Self-destruct** any of your limpets from the list to free a slot. The limpet is destroyed, not refunded, and the carrier takes no damage.

### If You Are the One Being Tracked

There is exactly one counterplay: the **limpet detection sweep** at any starport Shipyard, for a flat **10,000 cr**. It removes every tracker from your ship and — the premium part — reveals each planter's name and the sector where they planted. Fair warning: **the shipyard charges the full 10,000 cr even if your hull is clean.** Nothing else in the game detects limpets, so if you suspect you picked one up in enemy space, the sweep is the only way to know.

## Deployed Sector-Defense Fighters

Your planet's garrison can do more than wait for a siege. From the **Sector Defense card on the planet screen**, push garrison fighters out into the sector as automated defense. See [Planets](/guide/planets/) for how the garrison itself works.

- **Cap:** matches the planet's garrison cap — 500 base, doubled per Citadel level, up to 16,000.
- **Auto-engagement:** any hostile ship entering the sector — move or warp — is fired on immediately, before it can act, for up to **2,000 damage**. Damage hits shields first; overflow destroys fighters.
- **The fighters are not consumed** by these engagements. A standing defense force fires on every intruder, every time.
- Recall pulls fighters back into the garrison whenever you want them home.
- You get a feed and push alert each time your defenses engage someone.

Two caveats worth knowing. First, **pre-warp intel may not show these fighters** — a scouting player can warp into a heavily defended sector blind, which cuts both ways. Second, your own deployed fighter count is not currently displayed anywhere on the planet or sector screens — track what you deploy, because the interface will not remind you.

Stack the full perimeter on a valuable planet: mines for chip damage, sector-defense fighters for the heavy hit, garrison behind them for the siege. Each layer softens attackers for the next.

## Scanning for Deployables

The **Scan Deployables** button on the Bridge tab (1 turn) sweeps your current sector for hostile hardware — but temper your expectations. Detection is threshold-based: only heavy concentrations show up, and mines are especially elusive, revealing themselves only in large fields and even then unreliably. Limpets never appear on any scan.

The scan's most useful output is the **"Hostile defenses present in sector"** warning banner, which fires whenever any foreign deployable is in the sector — even ones below detection thresholds. That flag is the cheapest tripwire in the game for "someone has fortified this sector," even when the scan itself reports nothing.

For the full scanning toolkit, see [Scanners & Intel](/guide/scanners-intel/).

## Who Sees What

| Event | Owner sees | Victim/target sees |
|-------|-----------|--------------------|
| Mine detonation | Feed + push alert, per-sector mine list | Damage toast on arrival; public feed names them |
| Limpet latch | Feed + push alert, live tracking list | Nothing — silent until they pay for a sweep |
| Sector defense engages | Feed + push alert | Damage on entry; public feed names them |
| Foreign beacon | — | Visible when in the same sector |

## Inventory Management

Your beacon, mine, and limpet counts are visible on the Ship screen. Track them before long expeditions — you cannot deploy what you do not have. Beacons recall back to inventory; mines are consumed when they detonate; limpets are consumed on self-destruct or expiry. Nothing can be sold back.
