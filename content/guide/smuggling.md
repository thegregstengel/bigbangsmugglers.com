---
title: "Smuggling & Contraband"
date: 2026-08-04
draft: false
description: "The fence, the premium sale, customs scans, and hidden holds"
weight: 15
toc: true
---

*Accurate as of v2.0.18 (August 2026).*

## The catalog

Three contraband rows, each riding on a real commodity's price and volume.

| Contraband | Rides on | Buy | Max per purchase | Sell multiplier | Risk |
|---|---|---|---|---|---|
| Illicit Organics | Organics (1 vol) | 30 | 80 | ×2.0 | low |
| Stolen Equipment | Equipment (2 vol) | 40 | 50 | ×2.0 | medium |
| **Black Tech** | Equipment (2 vol) | 150 | 10 | **×3.5** | high |

Contraband lives in a separate cargo namespace from honest goods. The regular
sell action can never touch it — but **it still consumes your holds** at the
mapped commodity's volume.

## Buying

Requires clearing an **early ladder gate** and a port running the
`blackmarket` service: Pirate Bases, Black Markets and the Pirate Haven.

- **1 turn** per purchase, wallet only.
- Capped per transaction by the row.
- **Buying is never detected.** Nobody scans you at a fence.

Rim-going **trader NPCs** sometimes carry an off-market lot too — the same
level gate applies, priced at ×1.25 of the fence shelf. See
[NPCs](/guide/npcs/#trading-with-a-trader).

## Selling: two completely different actions

Selling sits behind its own gate, a bit deeper in the ladder than buying.
Both actions cost 1 turn.

### At a fence — safe and flat

Sell at a `blackmarket` port and you get the honest local price × **1.20**,
with **zero detection risk**. No roll, no fine, no alignment change.

That last part is worth reading twice. **Fence sales pay no alignment.** A
smuggler who only ever sells to fences can move enormous volume and remain
perfectly neutral all season.

### Anywhere else — the premium sale

Sell contraband at any other port and you get:

```
price = localSellPrice × rowMultiplier × regionHeat
```

...and you roll for detection.

| Region | Heat multiplier | Detection chance |
|---|---|---|
| `fed_core` | **×1.50** | **22%** |
| `fed_space` | ×1.40 | 18% |
| `inner` | ×1.25 | 12% |
| `middle` | ×1.15 | 8% |
| `outer` | ×1.00 | 4% |
| `outer_rim` | ×1.00 | 1% |

The inversion is the whole design: **the best prices are where you are most
likely to get caught.** Black Tech in the Federation core sells at 3.5 × 1.5
= **5.25×** the local equipment price, and 22% of those sales go wrong.

The detection roll is **not counterable**. Cloaking devices, stealth plating,
hidden compartments, the smuggler role — none of them touch it. Those counter
*customs scans*, which is a different system entirely.

### Getting caught on a sale

- **All the cargo is confiscated.**
- **Proceeds are zero.**
- **A fine of 50% of what the sale would have been**, minimum 500 cr, capped
  at your wallet.
- **−25 alignment.**
- The turn is still spent. There is no retry.

## Customs scans

Different system, different counters. A customs scan happens inside a
**patrol NPC encounter** during a move or a warp arrival. It is not something
you invoke.

### The chance

```
chance = 0.75
       − 0.50  Goods Cloaking Device
       − 0.30  Stealth Plating module
       − up to 0.08  smuggler role tier
floored at 5%
```

There is a **30-minute per-player cooldown** on scans. That cooldown is the
anti-farm mechanism, and it applies to clean scans too.

### If you're clean

The scan registers, you're waved through, and you earn **+2 alignment** with
an on-screen confirmation. This works now; it silently did nothing before
v2.0.8.

If you run honest cargo through patrolled space, patrols are your alignment
income, not a nuisance.

### If you're dirty

- **Auto-bribe** (a flag you can set on movement): pays **25% of street
  value**, clamped 500–25,000 cr, and costs **−2 alignment**.
- Otherwise: **all contraband seized**, a **10% fine**, and **−5 alignment**.

### Counters

| Counter | Effect | Notes |
|---|---|---|
| **Goods Cloaking Device** | −50pp | **Consumed by the attempt**, win or lose. 750 cr. |
| **Stealth Plating** module | −30pp | Permanent. Also +15pp escape and +12pp first strike. |
| **Smuggler role** | −2pp per tier, max −8pp | Free, earned by volume |
| **Pirate-line hull** | **Hides 25% of your holds outright** | The scan never happens for cargo under the threshold |
| **Hidden compartments** signature | +15% (T3) / +25% (T4) of holds, additive with the above | Plunder Barge, Marauder's Fortune |
| **The Phantom Manifest** (epic) | **+60% of holds** | Plus the pirate-line 25% |
| **False Manifest** module | One failed scan a day silently rerolls | Pirate-only, 20,000 cr, level-gated |
| **Patrol Transponder** module | Patrols never appear at all | Federation-only — mutually exclusive with being a smuggler in practice |

Stack a Marauder's Fortune (25% line + 25% signature = 50% of holds hidden)
with stealth plating and a max smuggler role and you are running at the 5%
scan floor with half your hold volume invisible.

## Hidden holds, precisely

"Hidden" volume is subtracted before the scan is considered at all. If your
contraband volume sits **under** the hidden threshold, **the scan does not
happen** — there is nothing for it to find.

```
hidden = floor(holds × 0.25)             pirate-line hull
       + floor(holds × abilityValue)     hidden_compartments signature
```

A 320-hold Pirate Leviathan hides 80 volume. A Marauder's Fortune at 210
holds hides 52 + 52 = 104 volume — 52 units of Black Tech, which is five
times the per-purchase cap.

## The career pays — provably

The game's configuration loader **refuses to start** with a contraband
catalog whose risk-adjusted expected value per hold-volume doesn't beat the
best honest route in every region. Detected sales lose the cargo *and* pay
the fine, and that's priced into the check.

You cannot ship a season where smuggling is a trap. That's an invariant, not
a promise.

## Playing it

**The disciplined fence run.** Buy at a Black Market, sell at another fence
at ×1.2. Safe, flat, zero alignment movement, no scan exposure from the sale
itself. Modest but completely reliable, and it's the only way to run the
Phantom Manifest epic ladder — which demands 7,500 units sold with **zero
sale-time busts all season**.

**The core run.** Black Tech bought at 150 in the rim, sold in `fed_core` at
5.25× the local equipment price. Enormous margins, a 22% chance per sale of
losing everything and −25 alignment, and you have to get through Federation
space — the most heavily patrolled region in the galaxy — to do it.

**The middle path.** `inner` and `middle` at ×1.25 and ×1.15 heat with 12%
and 8% detection. Better than the fence, survivable variance, and the regions
are more accessible than the core.

Note that repeated busts drive your alignment down fast (−25 each), which
eventually locks you out of the Stardock at −300 and takes the `fed_core`
market with it. The premium run erodes its own best market.

## Counters and statistics

Three counters track your career:

- `contrabandSold` — units. Drives the **Smuggler role** and the smuggler
  leaderboard, and only clean sales count.
- `contrabandBusts` — sale-time detections. Must be **exactly zero** at claim
  time for the Phantom Manifest.
- The **Shadow Trader** goal ladder pays at 10 / 50 / 180 units, and the Gold
  tier mints the *Shadow Broker* epithet insignia.
