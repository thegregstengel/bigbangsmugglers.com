---
title: "Turns, Credits & Basics"
date: 2026-08-04
description: "The turn cycle, buying turns, wallet versus bank, and streaks"
weight: 2
group: start
tags: [platform, progression]
changed_in: [2.3.0, 2.0.17, 2.0.13]
---

## The turn cycle

Turns are the whole pacing system. You get a fixed allowance, you spend it,
and you wait.

- **Cap:** 250 turns (season configuration).
- **Cycle:** 4 hours (season configuration, valid range 1–24).
- **Boundaries:** aligned to UTC — 00:00, 04:00, 08:00, 12:00, 16:00, 20:00.
- **Reset behavior:** full reset to the cap, not an increment.
- **Carryover:** none, ever. This is a design doctrine with no configuration
  knob behind it.

The reset is lazy: it lands the moment you next touch the game after a
boundary passes, so you never lose turns by being offline. When you're out,
the game tells you how many minutes remain until the next reset.

Note the split: the **turn cycle** is configurable, but the **world tick** —
planet production, market restock, port upkeep, garrison regrowth, shield
regen, ordnance decay — runs on a fixed 4-hour infrastructure schedule. Today
they coincide. In a season with a different cycle length they would not.

### What a turn costs

| Action | Turns |
|---|---|
| Move to a linked sector | 1 |
| Wormhole transit | 1 |
| Buy or sell cargo (per leg, any quantity) | 1 |
| Buy or sell contraband | 1 |
| Engage in combat | 1 |
| Fleet strike | 1 |
| Trade with a trader NPC (per deal) | 1 |
| Rob a trader NPC | 1 |
| Deploy or attack ordnance | 1 |
| Destroy a foreign beacon | 1 |
| Lay mines from a planet garrison | 1 |
| Active scan | 1 per ring (radius 1–3) |
| Claim a planet, build a structure | 1 |
| Raid a planet, capture a planet | 1 each |
| Attack a port | **3** |
| Capture or raze a port after the siege | 1 |
| Warp jump | `max(1, ceil(hops ÷ warpLevel))` |
| Tesseract jump | **25 flat** |
| Port repair | 0 |
| Landmark interaction | 0 |
| Banking, planting a limpet, deploying a beacon, redeeming bounty claims, vault transfers, planet storage | 0 |

Two turn discounts exist and both only touch **hop-based warp**: the Warp
Optimizer module (−1) and the Explorer role (−1 to −3). They stack, they
floor at 1 turn, and neither has ever applied to the Tesseract's flat 25.

### Buying turns

Ports running the **supplies** service — the three starports and every
Agricultural Port — sell provisions.

- **800 cr per turn.**
- **Maximum 5 turns per cycle.** This is a ration, not a per-purchase limit.
  The old guide got this wrong.
- You are charged only for turns actually delivered. If you're at 248/250 and
  ask for 5, you get 2, you pay 1,600, and 2 counts against your ration.
- A full tank returns `TANK_FULL` and charges nothing.
- Wallet only.

Turns also arrive as mission, event and streak rewards. Those grants are
cap-aware: they will not push you above the cap, and they never reduce a
tank that is somehow already over it.

## Credits: wallet versus bank

Two balances, and the distinction is the whole risk model.

**Wallet** is at-risk money. It pays for everything, and it is what gets
taken:

- looted when you lose a PvP fight (20–40% by the winner's alignment, capped
  by their hull tier)
- skimmed when your planet is raided (10%, max 5,000 cr)
- fined by customs, taken by pirate shakedowns, seized on arrest at dock
- drawn on every world tick for wages while you hold a
  [mercenary retinue contract](/guide/npcs/#the-tavern-retinue) — and the
  retinue deserts the moment the wallet can't cover a tick

**Bank** is safe storage. Nothing in the game takes credits out of it except
you. There are no deposit fees, no withdrawal fees, no interest, and no turn
cost — but **moving money in or out requires a teller**: you must be docked
at a port running the `banking` service, which means the three starports and
Federation Ports. (This changed in v2.0.13 — banking from deep space let a
player zero their lootable wallet from anywhere, which made credit robbery
effectively opt-out.) Your bank *balance* still spends from nowhere at all:
nothing buys out of the bank except the fall-through cases below.

Almost everything in the game is **wallet-only**. There are exactly three
exceptions that draw wallet first and then fall through to the bank:

1. **Ship repair.**
2. **Founding a corporation.**
3. **Posting a public announcement.**

Everything else — hulls, upgrades, drives, modules, items, provisions, intel,
defense contracts, bounty postings, planet claims, structures, starbases,
contraband — comes out of the wallet or not at all.

> The bank is a safe, not a bank. Loans, bonds and insurance are specified
> but not built; the module lands after the pilot. Nothing currently pays
> interest, and no credit is ever minted.

Corporations have their own bank, which is separate again. See
[Corporations](/guide/corporations-fleets/#the-corp-bank).

## Streaks

A **streak day** is any UTC day on which you spent at least one turn. Not a
login, not a full depletion — any turn-spending action. Two actions are
deliberately excluded because they cost 0 turns by default: landmark
interaction and port repair.

One missed day per streak is forgiven. Miss two and the streak resets to 1.

| Milestone | Credits | XP | Turns |
|---|---|---|---|
| Day 3 | 1,000 | 50 | — |
| Day 7 | 5,000 | 200 | 5 |
| Day 14 | 10,000 | 500 | 10 |
| Day 30 | 25,000 | 1,000 | 20 |

The streak **count** is account-level and survives season boundaries. The
**rewards** are seasonal — you need an active enrollment to claim them, and a
streak reset clears your claims so a fresh streak re-earns the same
milestones.

## The public feed

The galaxy keeps a news feed, and it is genuinely public. Battles are
reported (destroyed / drove off / fled), tier-3+ ship commissionings post,
planet claims and port captures post, ports shaking off their occupiers post,
new captains and season honors post. Ships lost to a minefield post, naming
both the victim and the mine's owner. Captain renames post publicly — the
one place the galaxy connects an old name to a new one. Goal-tier and
streak-milestone brags post too.

You can **react** to feed stories — five reaction types, pick as many as
apply.

You also have a private channel: your own events, and the "while you were
away" recap that lists what happened since you last looked and which planets
have full storage (production collects itself since v2.3.0, so a full
warehouse is the one thing that loses you output). Since v2.0.17 the private lane also tells you when
things happen to your *stuff*: someone destroyed your deployed ordnance,
someone swept off your limpet tracker, or your ordnance simply decayed away.

### Announcements

You can buy your way onto the public feed. A **player announcement** costs
**1,000 cr** (a pure sink — nobody receives it), is limited to **one per
turn cycle**, runs 3–280 characters through the profanity gate, and is
level-gated so a throwaway account is not a megaphone. Other players can
report an announcement to the moderation desk, so make it worth the credits.

Operators can also post galaxy notices of their own — those arrive as an
in-app banner you dismiss once, not just a feed line.

If you value operational secrecy, note what that means. Buying a capital-class
hull tells everyone. Losing a fight tells everyone. Claiming a planet paints
a target.

## Chat and mail

Corporation chat is the only in-galaxy chat: 500 characters, a 3-second
per-player cooldown and a 30-messages-per-minute corp-wide flood cap, with
the last 500 messages or 14 days of history retained — whichever is longer.
There are no direct messages between players. If you need to say something
to the whole galaxy, that's a [beacon](/guide/deployables/#navigation-beacons)
or a paid [announcement](#announcements).

Mail is account-scoped and works between seasons. Feedback goes straight to
the developers from inside the app; 2,000 characters, and it works whether or
not you're in a season.
