---
title: "Trader Reputation & Faction Alignment"
date: 2026-04-03
draft: false
description: "How trader reputation and faction alignment work, how they affect prices, and how to manage both systems"
weight: 4
toc: true
---

Your ship has two separate scores that affect how ports treat you.

**Trader Reputation (0--100):** This is whether merchants trust you as a trader. Hurt traders and your score drops. Ports everywhere charge you more while it's low. It slowly heals on its own over time.

**Faction Alignment (−1000 to +1000):** This is whether the Federation or the Pirates consider you an ally or an enemy. It only matters at ports those factions own. Beat up Federation patrols and Federation ports will rip you off. Fly Federation-friendly and you get discounts there instead.

The short version: Trader Rep follows you everywhere. Faction Alignment only kicks in at faction-owned docks.

---

## Trader Reputation

### What It Is

Trader Reputation is a score from 0 to 100 that tracks how you treat the independent traders in the galaxy. The default is 50 — neutral, no effect on prices. Falling below 50 triggers surcharges at every port you visit. Climbing above 50 earns discounts at every port you visit.

**This modifier applies at all ports — Federation, Pirate, and neutral alike.** There is no safe harbor.

### Price Effects

| Trader Rep | Effect at Every Port |
|---|---|
| 100 | −10% discount |
| 75 | −5% discount |
| 50 | No change |
| 25 | +5% surcharge |
| 0 | +10% surcharge |

The effect scales linearly between these points. A rep of 30 puts you at roughly +4% surcharge on everything you buy.

### What Lowers It

Killing neutral Trader NPCs is the main cause of damage. Each trader kill costs you **−5 Trader Reputation**. A handful of trader kills can push you from neutral into surcharge territory fast.

Fighting other NPCs (Federation Patrols, Pirate Raiders) does not directly affect Trader Reputation. How you treat traders is its own separate ledger.

### How to Recover

You cannot actively spend resources to restore Trader Reputation. Recovery is passive. Each turn cycle, your rep moves one point back toward neutral (50). If you're below 50, it ticks up by 1. If you're above 50, it ticks down by 1. Full recovery from the worst possible score (0) takes approximately 50 turn cycles, which is around 8 real-world days.

**The only reliable path to positive Trader Rep is to not kill traders.**

### Where to See It In-Game

Open the **Ship screen**, tap the **Factions** tab. Scroll to the **Trader Reputation** section. You'll see your current score (e.g. "22/100") and a progress bar. The label below the bar tells you your current status:

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

Unlike Trader Reputation, Faction Alignment **does not decay over time**. Where you stand today is where you stand until combat changes it.

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

Faction Alignment changes **exclusively through combat.** Trading, movement, missions, and idle time have no effect.

**Fighting NPCs:**

| NPC Type | Win | Lose |
|---|---|---|
| Federation Patrol | −6 alignment | −2 alignment |
| Pirate Raider | +4 alignment | +1 alignment |
| Neutral Trader | −1 alignment | 0 |

**Fighting players:**

| Defender Faction | Attacker Wins | Attacker Loses |
|---|---|---|
| Federation player | −8 alignment | −3 alignment |
| Pirate player | +6 alignment | +2 alignment |
| Neutral player | −2 alignment | −1 alignment |

If you're defending yourself against a Pirate player and you win, you gain +2 as a bonus on top of whatever combat normally awards.

### Where to See It In-Game

Open the **Ship screen**, tap the **Factions** tab. The **Alignment** section at the top shows your current score (e.g. "+340"), your current tier label (e.g. "True Neutral"), and a progress bar toward your next tier. Your faction badge (Federation / Pirate / Neutral) and rank title are shown in the card header.

---

## When Both Systems Stack

If you're buying goods at a Federation port and you have both a high alignment score (Federation-friendly) and a low Trader Reputation, both modifiers apply together — they multiply.

**Example:** Federation player, alignment +500 (−10% from faction) but Trader Rep of 10 (+9% surcharge from rep).

Combined multiplier: 0.90 x 1.09 = **0.98** (roughly a 2% net discount).

The port displays the combined modifier as a single banner — either a discount, a surcharge, or "Pricing modifiers cancel out" if they exactly offset. When both factors are active, the banner label reads **Combined Discount** or **Combined Surcharge** and shows the net percentage.

---

## Common Questions

**Why is one player getting a surcharge at a neutral port and another isn't?**

Neutral/unincorporated ports never apply Faction Alignment surcharges. The surcharge you're seeing is from **Trader Reputation**, which applies everywhere. The two players have different Trader Rep scores — one has likely been killing traders and the other hasn't. Check the Trader Reputation bar in your Factions tab.

**My Alignment Score is 32 — why am I paying more?**

An alignment of 32 puts you in the Neutral (True Neutral) range. Faction Alignment at a neutral port does nothing. Check your Trader Reputation score. If it's below 50, that's the source of the surcharge.

**Will trading more improve my Trader Reputation?**

No. Trading is neutral — it neither raises nor lowers Trader Rep. The only thing that hurts it is killing neutral Trader NPCs. The only thing that heals it is time (1 point per turn cycle toward neutral).

**Does Faction Alignment decay?**

No. Your alignment score stays wherever combat puts it, indefinitely. There is no passive drift. The only change mechanism is combat.

**Do I need to be Federation or Pirate to get good trade prices?**

Only if you're trading at faction-owned ports. At neutral and unincorporated ports, alignment is irrelevant. Focus on keeping your Trader Reputation at or above 50 — that's the modifier that follows you everywhere.
