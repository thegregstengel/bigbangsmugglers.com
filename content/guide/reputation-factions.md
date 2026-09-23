---
title: "Factions, Alignment & Standing"
date: 2026-08-04
description: "The two axes, how to earn them, and every gate they control"
weight: 14
group: compete
tags: [factions]
changed_in: [2.3.0, 2.0.8]
---

There are two numbers, they are not the same thing, and confusing them will
cost you money.

**Alignment** is *which side you're on*. One score, ranging from −1,000
(Syndicate) to +1,000 (Federation), zero at the start.

**Standing** is *what a side owes you*. Three separate scores — Federation,
Syndicate and Merchant Guild — earned by service and **decaying 1% every
day**.

You can be a Federation Admiral by standing and a Scourge by alignment. They
move independently.

> Trader reputation from 1.x is gone. It is now **Merchant Guild standing**:
> same ±10% price band, but it is a real faction score with a rank ladder and
> daily decay.

## Alignment

### The tiers

| Alignment | Tier |
|---|---|
| ≥ +900 | Paragon |
| ≥ +750 | Hero |
| ≥ +600 | Champion |
| ≥ +500 | **Ally** — Federation membership |
| > +250 | Law-Leaning |
| −250 to +250 | True Neutral |
| < −250 | Chaos-Leaning |
| < −500 | **Rogue** — Syndicate membership |
| < −600 | Villain |
| < −750 | Terror |
| ≤ −900 | Scourge |

### The three thresholds that matter

| Threshold | What it controls |
|---|---|
| **±300** | PvP classification, NPC aggression, and **capital docking** |
| **±500** | Membership: T3+ faction hulls, faction missions, faction tech modules |
| **±750** | Elite content: the elite faction season arcs |

## How to actually earn alignment

This is the section the old guide never had, because most of it didn't work
until v2.0.8. It works now.

### Lawful (positive)

| Deed | Alignment | Notes |
|---|---|---|
| **Pass a customs scan with clean holds** | **+2** | 30-minute cooldown. The steady income. |
| **Survive or beat a pirate attacker** | **+2** | Fires on NPC ambushes — the common case |
| Beat a Pirate-aligned player | +6 (+2 on a loss) | |
| Beat pirate NPC raiders | +4 (+1 on a loss) | |
| Daily lawful missions | +5 to +15 | Pirate hunts, bounty work, honest hauling |
| **Federation faction missions** | **+25** | Requires ±500 membership and 1,000 standing |
| **Elite Federation season arc** | **+30** | Requires \|alignment\| ≥ 750 |
| Claim a planet in Federation territory | **+250** | Needs alignment ≥ +100 first |
| Siege an underworld port | +10 | Yes, really — hitting pirates is lawful |

### Criminal (negative)

| Deed | Alignment |
|---|---|
| Attack a Federation-aligned player | −8 (−3 on a loss) |
| Attack Federation forces | −6 (−2 on a loss) |
| Attack a neutral player | −2 (−1 on a loss) |
| **Contraband sale detected** | **−25** |
| Siege a Federation-aligned port | −25 |
| Siege a neutral port | −10 |
| Caught in a customs scan | −5 |
| Bribe a patrol out of a scan | −2 |
| **Rob a trader NPC** | **−10** — plus Syndicate standing, a Merchant Guild hit, and Federation heat in the lanes |
| Underworld daily missions | −10 to −15 |
| **Syndicate faction missions** | **−25 / −30** |
| Claim a planet in pirate territory | **−250** |
| **Jettison mining workers** | **−10 per worker**. Dump them from your hold; since v2.3.0 this is the fast road to the pirate side |

### The realistic paths

**To Federation membership (+500):** the fastest route is missions. Two
faction-gated dailies at +25 apiece, or four lawful dailies at +12–15, plus
+2 for every clean customs scan you pass while trading. A trader who runs
honest cargo through Federation space and passes scans drifts upward without
trying. Claiming a planet in Federation space with ≥+100 alignment is a
single +250 jump.

**To Syndicate membership (−500):** contraband does it fast, but only when
you get *caught* (−25 per detected sale) or bribe your way out (−2). The
reliable criminal path is the underworld daily missions and the Syndicate
faction missions at −25 to −30, plus attacking lawful targets. Claiming a
planet in pirate territory is a single −250 jump. And since v2.3.0 there is
a blunt instrument: **jettison mining workers** at −10 each. Fifty workers
cost 15,000 cr at any recruitment desk and buy a −500 swing in one action.

**Note the asymmetry**: fence sales are undetectable and therefore pay *no*
alignment at all. A disciplined smuggler who only ever sells to fences can
move enormous volume and stay neutral forever.

**Getting back**: alignment is bidirectional and clamped at ±1,000. Nothing
is permanent. But a Scourge who wants to go straight has to earn +1,500 in
lawful deeds, and cannot dock at the Stardock to buy Federation missions
until they cross −300.

## What alignment buys you

### The benefit curve

One table, three uses: your combat bonus, your service discount at
own-faction ports, and the number on your standing card.

| \|Alignment\| | Benefit |
|---|---|
| 500 | 2% |
| 600 | 3% |
| 750 | 4% |
| 900 | 5% |

The **combat bonus** multiplies both your attack and defense power. The
**service discount** takes that percentage off repairs, hulls, upgrades,
drives and restock at ports of your own faction.

### The price band

At **faction-priced ports only** — Federation Ports, the Stardock, Pirate
Bases and the Pirate Haven — your alignment moves what you pay, linearly:

- **Friendly side:** buys scale down to **−20%** at ±1,000.
- **Hostile side:** buys scale up to **+50%**, *and* your sells are penalized
  by the inverse.

There is no friendly *sell* bonus. Discounts only ever help what you pay,
never what you're paid — a sell-side bonus would break the market's
round-trip rule. The combined discount is also clamped so it can never invert
the spread.

The Merchant Exchange and every neutral archetype **never** alignment-price.
Black Markets are excluded too — their economics belong to the fence spread.

### Docking gates

| Capital | Denies |
|---|---|
| **Stardock** | Alignment below **−300** |
| **Pirate Haven** | Alignment above **+300** |
| Merchant Exchange | Nobody |

"Docking" means opening the port's screen at all. Everything else in the
galaxy is open to anyone.

This is why the Merchant Exchange matters so much to a committed criminal:
it is the one full-service port — shipyard, repair, upgrades, banking,
supplies, price board — that a Scourge can walk into.

### Hull locks

Tier 1 and 2 faction hulls sell to anyone standing on the right floor.
**Tier 3, 4 and 5 faction hulls require ±500 alignment** on that side.

The neutral spine never locks, at any tier. Refusing to pick a side costs you
the Federation +10% shields and the Pirate +0.10 escape — not access to the
endgame.

### Faction tech modules

**Patrol Transponder** (Federation) and **False Manifest** (Pirate) both
require ±500 on their side.

### Arrest at dock

If a faction holds a bounty on you and you try to *do* anything at its
capital:

- Wallet covers it: **seized**, warrant cleared, publicly announced, and that
  action fails. The next one works.
- Wallet short: refused, nothing seized.

Only the wallet. Never the bank. See [Bounties](/guide/bounties/#arrest-at-dock).

## Standing

Three scores, one ladder, thresholds **0 / 1,000 / 2,500 / 5,000 / 10,000**:

| Faction | Ranks |
|---|---|
| Federation | Cadet, Lieutenant, Commander, Captain, Admiral |
| Syndicate | Crew, Quartermaster, First Mate, Captain, Pirate Lord |
| Merchant Guild | Peddler, Broker, Trader, Merchant, Magnate |

Ranks are cosmetic except for the **1,000 member-tier gate** on faction
missions.

### Earning standing

| Deed | Standing |
|---|---|
| Kill an enemy-faction NPC | **+15 × NPC tier** |
| Kill your own faction's NPC | **−15 × NPC tier** |
| Capture a port in enemy space | +100 |
| Attack a faction's port | −15 |
| **Every honest trade leg** | **+1 Merchant Guild** |
| Rob a trader NPC | +5 × NPC tier Syndicate, **−25 Merchant Guild** |
| Faction daily mission | +100 |
| Elite faction season arc | +400 |
| Goal ladder tiers | +50 to +150 |

### Decay is the point

**Standing decays 1% per day.** It is a garden, not a ratchet.

Do the arithmetic before you chase a standing number. Holding 2,500 standing
costs about 125 points of fresh service *every day* — that's roughly two
faction missions daily, forever. This is exactly why the epic hulls demand
standing floors rather than lifetime totals: you cannot bank it once and walk
away.

Merchant Guild standing at +1 a trade leg needs about 133 legs a day to
converge on 3,000 by day 30. That is over half of every turn you have, all
season, on the trade button.

### The guild band

Merchant Guild standing gives a buy-side discount at **every port in the
galaxy**, scaling linearly to **−10%** as standing approaches 1,000.

It is the only faction benefit that applies universally, it costs nothing but
trading honestly, and every trader should have it saturated inside a week.

## The war

Faction standing and faction deeds feed a **war score**: enemy NPC kills
count ×1, enemy port captures ×10, faction missions ×3. The winning faction
takes the season's campaign medal at the closing ceremony.

## Smuggling: the opposite path

The criminal career is not "the same game with a different sign". It is
structurally different, and worth understanding even if you never run
contraband.

| | Honest trading | Smuggling |
|---|---|---|
| Where you buy | Any port that sells | `blackmarket` service only |
| Where you sell | Any port | Fence (safe, flat ×1.2) or any port (premium, risky) |
| Price ceiling | Anchor spreads | ×2.0 to ×3.5 on the local price, ×1.5 in Federation space |
| Risk | Getting robbed | **Customs scans and sale detection** |
| Alignment | None from trading | −25 per detected sale, −5 per bust, +0 from fence sales |
| Guild standing | +1 per leg | none |
| Best region | Wherever the spread is | **Federation core** — the highest premium *and* the highest detection |

The elegant part is the inversion. Honest trade is safest and most profitable
in the middle of the map; contraband is most profitable exactly where it's
most likely to get you caught — Federation core pays a ×1.50 premium and
catches 22% of sales.

The career is guaranteed to pay: the game's own configuration validator
refuses to load a contraband catalog whose risk-adjusted return per hold
doesn't beat the best honest route.

See [Smuggling & Contraband](/guide/smuggling/).
