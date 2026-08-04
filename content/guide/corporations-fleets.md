---
title: "Corporations & Fleets"
date: 2026-08-04
draft: false
description: "Founding, roles, the corp bank, policies, fleets and held ports"
weight: 17
toc: true
---

*Accurate as of v2.0.8 (August 2026).*

## Founding

| | |
|---|---|
| Level gate | **5** |
| Cost | **50,000 cr** — wallet first, then bank |
| Name | 3–50 characters, unique in the galaxy |
| Member cap | `max(10, seasonPlayerCap ÷ 5)` |

Corp founding is one of exactly two things in the game the bank can pay for.
The other is ship repair.

**Join policy** is set at creation and changeable by the leader:

- `open` — anyone joins instantly
- `request` — applications go to a queue leaders and officers approve
- `invite` — invitation only

## Roles

Three roles, and the ladder is deliberately blunt.

| Action | Leader | Officer | Member |
|---|---|---|---|
| Invite | ✅ | ✅ | |
| Approve join requests | ✅ | ✅ | |
| Set policies | ✅ | ✅ | |
| Set the notice | ✅ | ✅ | |
| Kick | any non-leader | members only | |
| Promote / demote | ✅ | | |
| Transfer leadership | ✅ | | |
| Set join policy | ✅ | | |
| Withdraw from the bank | ✅ | ✅ | only if policy allows |

Nobody can kick the leader. Promotion goes member → officer; leadership can
only be transferred to someone who is already an officer.

**A leader with other members cannot leave the corporation, leave the season,
or delete their account** until they hand leadership over. The last member
out dissolves the corp.

## The corp bank

A shared balance, separate from every personal wallet and bank.

- **Deposits come from your wallet only.**
- **Withdrawals** require Leader or Officer, *or* the `bank.spend` policy
  toggle — which defaults **off**.
- Transaction bounds: 1 to 10,000,000 cr.
- **Fleet strike loot goes here**, not to the leader's wallet.
- At season end, the corp bank is distributed **pro rata** among members.

## Policies

Four toggles, and they are real gates enforced at the module that owns the
resource — not decoration.

| Policy | Default | Controls |
|---|---|---|
| `storage.view` | **on** | Seeing planet storage contents |
| `storage.deposit` | **on** | Depositing into a corp planet's storage |
| `storage.withdraw` | **off** | Taking out of it |
| `defenses.view` | **on** | Seeing corp deployables |
| `defenses.place` | **on** | Deploying under the corp |
| `defenses.clear` | **off** | Removing them |
| `planet.build` | **off** | Non-owners building structures on a corp planet |
| `bank.spend` | **off** | Members withdrawing from the bank |

The defaults are "contribute freely, take carefully". Every toggle that lets
a member *remove* something starts off.

## Chat

The only chat in the game. 500 characters, a 3-second per-player cooldown,
a 30-messages-per-minute corp-wide flood cap, profanity filtered. History
retains the **last 500 messages or 14 days, whichever is longer**.

There are **no direct messages** between players. If you need to reach
someone outside your corp, you leave a beacon in a sector or you don't.

Leaders and officers can also set a **notice** (500 characters) that every
member sees.

## Fleets

A fleet is up to **three ships** from the same corporation operating as one.

| | |
|---|---|
| Form a fleet | Level **15**, must be in a corp |
| Join a fleet | Level **10**, same corp only |
| Cap | **3 ships** |

The leader leaving disbands the fleet.

### Fleet strikes

Leader-only, **1 turn**, and it runs exactly the same gates as solo combat.

The requirement people miss: **every member you want counted must be in the
leader's sector with an active ship**. Members elsewhere contribute nothing.
The leader's own ship must be battle-ready. Otherwise you get
`NOT_ASSEMBLED`.

- **Loot goes to the corp bank.**
- **Attrition is redistributed across members** — everyone bleeds, not just
  the leader.
- **Any member's hull can reach zero**, and that member goes through the full
  destruction and pod flow, losing their ship, its upgrades, its cargo and
  every remaining turn.
- Fleet kills apply the same alignment, statistics and immunity consequences
  as solo kills.
- The **leader** personally earns any faction bounty claims.

A fleet is not a way to fight safely. It is a way to concentrate three ships'
worth of power into one engagement, and it spreads the losses across three
hulls when it goes wrong.

## Holding ports

Corporations can besiege and hold ports. Everything except the three
starports and Federation Ports is capturable.

### Sieging

| | |
|---|---|
| Level gate | **15** |
| Turn cost | **3** per attack |
| Cooldown | **1 hour** per port |
| Blocked by | An active 24-hour post-capture truce |

Siege math is the same shape as a planet raid: fighters ×0.8 (×1.2 with
Combat AI), shields ×1.2, torpedoes ×2.0 against a garrison seeded from the
port's stock value (`stockValue ÷ 100,000`, clamped 30–200) and regrowing 10%
per tick.

A win skims 0.1% of stock value, capped at 2,000 cr. A defeat costs you 75%
of your fighters and 75% of your defense pool as damage — **which can destroy
your ship.**

Alignment cost per attack: **−25** at a Federation-aligned port, **−10** at a
neutral one, **+10** at an underworld port.

### Capturing and holding

After a successful siege, `capture` costs 1 turn and **requires a
corporation**. Your corp's hold cap is `max(1, members ÷ 3)` — a 12-member
corp can hold four ports.

A held port:

- skims **50%** of its tax revenue to the corp bank (the rest burns)
- charges **corp members half tax**
- charges everyone else **+1 percentage point**
- costs upkeep every tick: `max(500, stockValue × 0.25%)`
- **reverts to neutral after 2 consecutive unpaid ticks**

That last line is the whole balance. A corporation that captures more than it
can fund watches its ports shake off the occupation publicly, on the feed.

`raze` is the alternative to holding: 1 turn, loot 10% of stock value capped
at 25,000 cr, and the port is wrecked rather than held. `release` hands a
held port back voluntarily.

## Corp alignment

Corporations display a faction character and their leaders carry
faction-flavored titles.

**Today this is cosmetic.** Corp alignment does not gate membership, change
prices, alter combat, or restrict what a corp can hold. Individual player
alignment does all of that work. If a corp badge implies otherwise, the badge
is flavor.

## What a corp actually gets you

Concretely, and nothing else:

1. **Fleets** — three ships in one engagement.
2. **Held ports** — half tax for members, a revenue skim to the bank.
3. **Shared planet storage and building**, subject to policy.
4. **A shared bank**, distributed pro rata at season end.
5. **Chat** — the only communication channel in the game.
6. **Landing protection on corp planets.**
7. **Corp-internal planet deed transfers.**
8. **Corp-mates cannot attack each other**, ever.
9. **Corp Champion medals** at the ceremony for every member of the
   top-scoring corp.
