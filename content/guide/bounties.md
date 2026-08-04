---
title: "Bounties"
date: 2026-08-04
draft: false
description: "Posting, collecting, faction claims, and buying off your warrant"
weight: 10
toc: true
---

*Accurate as of v2.0.8 (August 2026).*

There are two kinds of bounty and they pay out completely differently.

## Player-posted bounties

Anyone at level 3 or above can put a price on a rival's head at a **bounty
office** — the `tavern` service, which runs at the Stardock and at Pirate
Bases.

| | |
|---|---|
| Amount | 500 – 100,000 cr |
| Posting fee | +10% on top |
| Payment | Wallet only |
| Expiry | 7 days |
| Restrictions | Not on yourself; target must be in your galaxy |

Posting 50,000 costs you 55,000.

**A player bounty pays cash immediately** to whoever beats the target in PvP.
No paperwork, no travel, no registry. Win the fight, the money lands.

## Faction bounties

Faction bounties are generated automatically. Kill enough of a faction's
people and that faction posts a warrant on you.

```
amount = min(500 × tierMultiplier × sqrt(kills), 500,000)
tierMultiplier = 1, 2, 4, 8, 16    by your hull tier
```

The **square root** matters: heat grows fast at first and then flattens. Your
tenth kill roughly triples the price of your first; your hundredth is only
just over three times your tenth. A tier-5 hull multiplies the whole thing by
16.

**Faction bounties never expire.**

### The two-step claim

Beating a captain who carries a faction bounty does **not** hand you cash. It
mints a **bounty claim** — a redeemable ticket that never expires.

To turn claims into credits you go **in person to the issuing registry**:

| Faction | Registry |
|---|---|
| Federation | The **Stardock** sector |
| Syndicate | The **Pirate Haven** sector |

Redemption costs **0 turns** and cashes every claim of that faction at once.

The obvious problem is also the design: a captain who spends their time
hunting Federation-wanted pirates has to sail into pirate space to earn
claims and back to the Stardock to cash them. And a Federation registry
denies docking to anyone below −300 alignment.

In a fleet strike, the **leader** personally earns the claims.

## Being wanted

Your standing card shows a **wanted** entry for each faction that holds a
warrant on you. That warrant does three things:

1. **Every player in the galaxy can see the price** and collect it.
2. **Patrols and pirates shoot on sight**, overriding their normal aggression
   rules.
3. **The issuing faction's capital arrests you at the door.**

### Arrest at dock

Try to do anything at a faction capital that holds a warrant on you:

- **If your wallet covers the bounty:** it is seized up to the bounty amount,
  the warrant clears, the arrest posts to the public feed, and **that action
  fails** with `ARRESTED_AT_DOCK`. Retry and it works — you're clean now.
- **If your wallet is short:** you're refused with `DOCKING_DENIED_BOUNTY`
  and nothing is seized.

Only the **wallet** is ever seized. Your bank is untouched. Which means the
cheapest way to survive an arrest is to have nothing in the wallet — and the
cheapest way to clear a warrant on your own terms is to walk in carrying
exactly the bounty amount.

Looking at prices is a query and only checks alignment. **Buying anything is
a mutation and runs the arrest check.** You can window-shop while wanted.

### Paying it off

You can also settle directly with `payoff`, naming the faction
(`federation` or `pirate_syndicate`). Your wallet must cover the full amount.
No fee, no discount, no negotiation.

## The board

The bounty board shows:

- every active bounty in the galaxy
- your own unredeemed faction claims
- the total head money currently on you

The **Most Wanted** leaderboard ranks players by the sum of active bounties
on their heads. The **Bounty Hunter** leaderboard ranks by bounty **credits
earned** — player payouts at the kill plus faction claims at redemption —
with heads collected as the tiebreak.

## Making a living at it

Bounty hunting is a real career with real numbers behind it:

- The **Bounty Hunter** goal ladder pays out at 3 / 12 / 40 heads.
- The daily **Bounty Board** and **Bounty Spree** missions pay 7,000–8,000 cr
  plus lawful alignment.
- The epic **Warrant** hull demands 100 heads *and* 1,000,000 cr in bounty
  money, and grants limpet trackers that never expire.
- The epic **Writ of the Council** demands 50 redeemed *Federation* claims
  and 2,500 held Federation standing.

The counters that matter are `bountiesCollected` (heads) and
`totalBountyCreditsEarned` (money). They are tracked separately and the epic
ladders want both.
