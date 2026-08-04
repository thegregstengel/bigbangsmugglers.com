---
title: "NPCs & Encounters"
date: 2026-08-04
draft: false
description: "Pirates, patrols, traders, named captains, and every way out"
weight: 13
toc: true
---

*Accurate as of v2.0.8 (August 2026).*

## The three types

| Type | Base rate per move | Never appears in | Max per sector | Drops |
|---|---|---|---|---|
| **Pirate** | 3.0% | Federation territory | 3 | 500–2,000 cr |
| **Trader** | 2.0% | — | 2 | 100–500 cr |
| **Patrol** | 1.5% | Pirate territory | 2 | **nothing** |

Region multiplies the base rate:

| Region | Pirate | Trader | Patrol |
|---|---|---|---|
| `fed_core` | — | — | ×4.0 |
| `fed_space` | — | ×0.5 | ×2.5 |
| `inner` | ×0.5 | ×1.0 | ×1.5 |
| `middle` | ×1.0 | ×1.2 | ×1.0 |
| `outer` | ×1.5 | ×0.8 | ×0.5 |
| `outer_rim` | **×2.0** | ×0.5 | — |

Pirates take priority over patrols, which take priority over traders. One NPC
maximum per roll.

Loot scales by tier: ×0.75 / ×1.00 / ×1.25 / ×1.50 / ×1.75 at tiers 1–5.

**Patrols drop nothing.** Killing one buys you a Federation warrant and
nothing else. That is deliberate.

## Aggression

**Patrols never ambush. Traders never ambush.** Only pirates start fights,
and only against people they consider fair game:

| Your alignment | In pirate territory | Elsewhere |
|---|---|---|
| ≥ +300 (Federation) | **100%** | 66% |
| Between | 66% | 33% |
| ≤ −300 (Pirate) | **never** | **never** |

Pirates never ambush a Pirate-aligned captain. Being deeply criminal is, in
the most literal sense, safe.

Two overrides:

- **A faction warrant on your head makes patrols and pirates shoot on
  sight**, regardless of the table above.
- The **Patrol Transponder** module (Federation-only) means patrols never
  materialize at all. The epic **FSS Writ of the Council** does the same and
  doesn't care about your current alignment.

## Encounters that aren't fights

An NPC that doesn't ambush becomes a **pending encounter**. Every option
below costs **0 turns**.

| Option | What happens |
|---|---|
| **Engage** | 1 turn, resolves as combat, no retreat roll |
| **Surrender** (pirate) | They take **30% of your cargo units**. If your holds are empty, **10% of your wallet** instead, capped at 5,000 cr. Never both. No fight, no alignment change. |
| **Jettison** | Dump **25% of cargo** as a distraction. Guaranteed escape from a pirate. |
| **Jettison contraband** | Dump **all** contraband. The free alternative to submitting to a scan when you're dirty. |
| **Bribe a pirate** | 500 / 1,500 / 4,000 / 10,000 / 25,000 cr by tier. 65% success, **+15pp if you're pirate-aligned** below −300. −1 alignment on success, −2 on failure. |
| **Bribe a patrol** | 60% success. Failure costs a 2,000 cr fine. |
| **Submit to a scan** | Clean holds: **+2 alignment**. Dirty: seizure. |
| **Trade** | Buy and sell with a trader NPC at a **×1.5 markup** over engine prices, up to 1,000 units. |
| **Rob a trader** | Requires alignment **≤ −500**. 60% success. Purse 2,000 / 5,000 / 12,000 / 25,000 / 50,000 cr by tier. Makes the trader faction hostile for 4 hours. |

Fleeing a pending encounter means simply letting it expire — pending contacts
time out on their own.

Confirming a fight re-rolls it under the **stored seed**, so the result is
deterministic. Reloading the screen does not reroll the dice.

## Customs scans

Patrol encounters can trigger a **customs scan**. This is not a menu option
you pick; it happens inside a patrol contact during a move or a warp arrival.
See [Smuggling](/guide/smuggling/#customs-scans) for the full mechanics.

The part everyone needs to know: **passing a customs scan with clean holds
pays +2 alignment**, with a 30-minute cooldown that stops you farming it. If
you fly lawfully, patrols are not a nuisance — they are your standing income.

## Warp interruption

An NPC can stop you mid-warp. The journey truncates where you were
intercepted and turns are refunded proportionally for the hops you didn't fly.

The per-hop rate is bounded so **no journey exceeds a 30% total chance** of
being interrupted, however long it is. Immune players skip the roll.

An interrupted warp used to treat everybody as neutral. It doesn't anymore —
real alignment and real warrants apply mid-flight.

## The living world

Transient NPCs are not furniture:

- Untouched NPCs **despawn after 2 hours**.
- Survivors **wander to a linked sector with 20% chance per world tick**.
- Trader NPCs actually **travel port to port**, picking destinations 3 to 10
  hops out.

## Named NPCs

Ten named characters generate per galaxy — five pirates, five Federation —
and they roam their assigned regions permanently.

| Name | Title | Type | Tier | Roams | Bounty |
|---|---|---|---|---|---|
| Redmaw Vex | the Warlord | Pirate | 5 | `outer_rim` | **150,000** |
| Grim Tally | the Butcher | Pirate | 4 | `outer_rim` | 75,000 — **always ambushes** |
| Iron Hessa | the Corsair Queen | Pirate | 4 | `outer`, `outer_rim` | 60,000 — escape 0.60 |
| Blackline Kord | the Smuggler King | Pirate | 4 | `middle`, `outer` | 60,000 — drops contraband |
| Saber Quill | the Phantom | Pirate | 3 | `outer` | 30,000 — escape 0.50, rarely sighted |
| Adm. Aster Vale | Fleet Admiral | Patrol | 5 | `fed_core` | — |
| Cmdr. Silva Trask | Border Commodore | Patrol | 4 | `inner` | — |
| Cmdr. Ren Okafor | Customs Marshal | Patrol | 4 | `fed_space`, `inner` | — |
| Capt. Odessa Rhee | Bounty Warden | Patrol | 4 | `inner`, `middle` | — |
| Maj. Callum Dray | the Inquisitor | Patrol | 3 | `fed_space` | — |

When a named NPC moves, it usually posts a **sighting rumor** to the feed —
about 75% of the time by default, and Saber Quill only 25%. Rumors are
deliberately fuzzed: they report a sector **within a couple of hops** of the
real one, never the exact position.

### Grinding a boss down

Damage you deal a named NPC **sticks to its row between fights**. It
regenerates **25% of its spawn strength per world tick** — roughly sixteen
hours from wreck to full.

So Redmaw Vex is not a wall you either clear or don't. Four good runs inside
one day will grind him down. Come back a week later and he's fresh.

**Losing pays nothing.** Defeat awards no XP, which closed the old loop of
pulling an unbeatable boss for a turn a time as an XP faucet.

### The Bane

The **first player to kill a named NPC** in a season earns a unique ship
prefix insignia: *"«Name»'s Bane"*. One per named NPC per season. Nobody else
can ever have it that season.
