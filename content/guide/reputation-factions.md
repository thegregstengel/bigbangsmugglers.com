---
title: "Trader Reputation & Faction Alignment"
date: 2026-07-02
draft: false
description: "How trader reputation and faction alignment work, how they affect prices and access, and how to manage both systems"
weight: 9
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

Your ship has two separate scores that affect how the galaxy treats you.

**Trader Reputation (0--100):** This is whether merchants trust you as a trader. Hurt traders and your score drops. Ports everywhere charge you more while it's low. It drifts back toward neutral on its own over time — in both directions.

**Faction Alignment (−1000 to +1000):** This is whether the Federation or the Pirates consider you an ally or an enemy. It moves prices at faction-owned ports, and it gates access galaxy-wide — starport docking, contraband scans, planet claims, and more.

The short version: Trader Rep follows you everywhere. Faction Alignment sets your prices at faction docks and decides which doors are open to you at all.

Both scores reset at the start of every season — a fresh moral slate each campaign.

---

## Trader Reputation

### What It Is

Trader Reputation is a score from 0 to 100 that tracks how you treat the independent traders in the galaxy. The default is 50 — neutral, no effect on prices. Falling below 50 triggers surcharges at every port you visit. Climbing above 50 earns discounts at every port you visit.

**This modifier applies at all ports — Federation, Pirate, and neutral alike.** There is no safe harbor.

### Price Effects

**Buying (purchase prices):**

| Trader Rep | Effect at Every Port |
|---|---|
| 100 | −10% discount |
| 75 | −5% discount |
| 50 | No change |
| 25 | +5% surcharge |
| 0 | +10% surcharge |

**Selling (what ports pay you):** the same score works in reverse when you sell — good standing means ports pay you more.

| Trader Rep | Sell Price Effect |
|---|---|
| 100 | ~+11% bonus |
| 75 | ~+5% bonus |
| 50 | No change |
| 25 | ~−5% penalty |
| 0 | ~−9% penalty |

Both effects scale linearly between these points. A rep of 30 puts you at roughly +4% surcharge on everything you buy.

### What Moves It

| Action | Trader Rep Change |
|---|---|
| Kill a neutral Trader NPC | **−5** (plus traders turn hostile toward you for 4 hours) |
| Rob an NPC trader | −3 |
| Buy from or sell to an NPC trader in space | **+1 per transaction** |

Fighting other NPCs (Federation Patrols, Pirate Raiders) does not affect Trader Reputation. How you treat traders is its own separate ledger.

### Recovery and Decay

Each turn cycle (every 4 hours), your rep moves one point back toward neutral (50). **This is symmetric**: if you're below 50 it ticks up by 1, and if you're above 50 it ticks *down* by 1 — an earned discount erodes just like a bad record does. Full travel from an extreme (0 or 100) back to 50 takes around 8 real-world days.

There is one active lever: **trading with the NPC traders you meet in space** gives +1 per transaction. That's how you climb above 50 — and how you stay there against the decay.

### Where to See It In-Game

Open the **Ship screen**, tap the **Stats** tab, and tap the **Reputation** card to expand it. You'll see your current score (e.g. "22/100") and a progress bar. The label below the bar tells you your current status:

- *"Good standing — discount at ports"* (rep >= 50)
- *"Low reputation — surcharge at ports"* (rep < 50)

The progress bar color changes as your rep drops: teal (50+), gold (30--49), red (below 30).

---

## Faction Alignment

### What It Is

Faction Alignment is an integer score from −1000 to +1000. It measures your relationship with the two major factions — the Federation and the Pirates.

- **Positive scores** mean you're Federation-aligned.
- **Negative scores** mean you're Pirate-aligned.
- **Between −499 and +499** means you're Neutral (independent, no faction affiliation).

Unlike Trader Reputation, Faction Alignment **does not decay over time**. Where you stand today is where you stand until your actions change it — or the season resets it to 0.

### Faction Membership

Your faction label is determined by your alignment score:

| Score Range | Faction |
|---|---|
| +500 to +1000 | Federation |
| −499 to +499 | Neutral |
| −500 to −1000 | Pirate |

Within each faction there are tiers that unlock benefits and mission types.

**Federation Tiers**

| Tier | Minimum Score |
|---|---|
| Ally | +500 |
| Champion | +600 |
| Hero | +750 |
| Paragon | +900 |

**Pirate Tiers**

| Tier | Score (most negative) |
|---|---|
| Rogue | −500 |
| Villain | −600 |
| Terror | −750 |
| Scourge | −900 |

**Neutral Sub-tiers** (no pricing effect, just flavor)

| Sub-tier | Range |
|---|---|
| Law-Leaning | +251 to +499 |
| True Neutral | −250 to +250 |
| Chaos-Leaning | −499 to −251 |

### Price Effects

Faction Alignment **only affects prices at Federation-owned and Pirate-owned ports.** Neutral and unincorporated ports always charge standard prices regardless of your alignment score.

At a faction port, the question is: are you a friend or an enemy?

- A Federation player at a Federation port gets discounts.
- A Pirate player at a Federation port pays surcharges.
- A Neutral player at any faction port pays standard prices.

**Buying (purchase prices):**

| Alignment Score | Federation Port | Pirate Port |
|---|---|---|
| +1000 | −20% discount | +50% surcharge |
| +500 | −10% discount | +25% surcharge |
| 0 | No change | No change |
| −500 | +25% surcharge | −10% discount |
| −1000 | +50% surcharge | −20% discount |

**Selling (what ports pay you):**

When you're the port's ally, they pay you more for goods. When you're the enemy, they pay less.

| Alignment Score | Federation Port (sell) | Pirate Port (sell) |
|---|---|---|
| +1000 | +25% bonus | −33% penalty |
| +500 | +11% bonus | −20% penalty |
| 0 | No change | No change |
| −500 | −20% penalty | +11% bonus |
| −1000 | −33% penalty | +25% bonus |

### What Changes It

Faction Alignment moves in response to a wide range of actions — combat is only one of them.

**Fighting NPCs:**

| NPC Type | Win | Lose |
|---|---|---|
| Federation Patrol | −6 alignment | −2 alignment |
| Pirate Raider | +4 alignment | +1 alignment |
| Neutral Trader | −1 alignment | 0 |

**Fighting players:** in PvP, the game classifies your target by the **faction of the ship hull they're flying**, not by their personal alignment score. A high-alignment player flying a pirate hull counts as a "Pirate player" for these deltas.

| Target's Ship Faction | Attacker Wins | Attacker Loses |
|---|---|---|
| Federation hull | −8 alignment | −3 alignment |
| Pirate hull | +6 alignment | +2 alignment |
| Neutral hull | −2 alignment | −1 alignment |

If you're defending yourself against a pirate-hull attacker and you win, you gain +2 as a bonus on top of whatever combat normally awards.

**Everything else:**

| Action | Alignment Change |
|---|---|
| Caught with contraband (customs or patrol scan) | −5 per bust |
| Bribe a pirate or a Federation patrol (success) | −1 |
| Failed Federation bribe | −2 (up to −7 total if the forced scan then catches contraband) |
| Submit to a patrol scan while clean | +2 |
| Rob an NPC trader | −2 |
| Jettison Mining Workers | −10 per worker |
| Attack a pirate or black-market port | +10 per attempt |
| Attack a commerce port in Federation territory | −25 per attempt, plus a Federation bounty on your head |
| Attack a port in neutral territory | −10 per attempt |
| Claim a planet in Federation territory | +250 |
| Claim a planet in pirate territory | −250 |
| Complete a Federation mission | +5 to +30, depending on the mission |
| Complete a pirate mission | −5 to −30, depending on the mission |

Ordinary port trading, movement, and idle time do **not** move alignment.

### Alignment Gates

Prices are only half the story. Alignment thresholds open and close doors across the galaxy:

| Threshold | Effect |
|---|---|
| Below −300 | Federation starports refuse you docking |
| Above +300 | Pirate starports refuse you docking |
| Above +300 | Federation contraband scans skip you entirely — customs and patrols never search your hold |
| At or below −500 | Meets the threshold to rob trading posts |
| +100 / −100 | Required to claim planets in Federation (+100) or pirate (−100) territory |

### Where to See It In-Game

Open the **Ship screen**, tap the **Stats** tab, and expand the **Reputation** card. The **Alignment** section shows your current score (e.g. "+340"), your current tier label (e.g. "True Neutral"), and a progress bar toward your next tier. Your faction badge (Federation / Pirate / Neutral) and rank title are shown in the card header.

---

## When Both Systems Stack

If you're buying goods at a Federation port and you have both a high alignment score (Federation-friendly) and a low Trader Reputation, both modifiers apply together — they multiply.

**Example:** Federation player, alignment +500 (−10% from faction) but Trader Rep of 10 (+8% surcharge from rep).

Combined multiplier: 0.90 x 1.08 = **0.972** (roughly a 3% net discount).

At the extremes the stack matters a lot: a maxed-out ally with perfect Trader Rep buys at 28% off, while a hated enemy with rock-bottom rep pays a 65% markup.

The port displays the combined modifier as a single banner — either a discount, a surcharge, or "Pricing modifiers cancel out" if they exactly offset. When both factors are active, the banner label reads **Combined Discount** or **Combined Surcharge** and shows the net percentage.

---

## Common Questions

**Why is one player getting a surcharge at a neutral port and another isn't?**

Neutral/unincorporated ports never apply Faction Alignment surcharges. The surcharge you're seeing is from **Trader Reputation**, which applies everywhere. The two players have different Trader Rep scores — one has likely been killing traders and the other hasn't. Check the Reputation card in your Stats tab.

**My Alignment Score is 32 — why am I paying more?**

An alignment of 32 puts you in the Neutral (True Neutral) range. Faction Alignment at a neutral port does nothing. Check your Trader Reputation score. If it's below 50, that's the source of the surcharge.

**Will trading more improve my Trader Reputation?**

Port trading is neutral — it neither raises nor lowers Trader Rep. But **trading with the NPC traders you meet in space gives +1 per transaction** — that's the one active way to raise it. Killing traders (−5) and robbing them (−3) are what hurt it.

**Does Faction Alignment decay?**

No. There is no passive drift — your alignment stays wherever your actions put it, until the next season resets it to 0. It moves through combat, smuggling busts, port attacks, planet claims, missions, and the other actions in the table above.

**Do I need to be Federation or Pirate to get good trade prices?**

Only if you're trading at faction-owned ports. At neutral and unincorporated ports, alignment is irrelevant to prices. Focus on keeping your Trader Reputation at or above 50 — that's the modifier that follows you everywhere. But keep an eye on the alignment gates: even a price-indifferent trader wants to stay above −300 to keep Federation starports open.
