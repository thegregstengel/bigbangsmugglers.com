---
title: "Combat"
date: 2026-08-04
draft: false
description: "How a fight resolves, hull versus shields, immunity, and fleets"
weight: 9
toc: true
---

*Accurate as of v2.0.8 (August 2026).*

Combat is instant and automatic. You engage, the server resolves the whole
fight in one shot, and you read the report. There is no round-by-round input.

## Before the dice: the gates

Every engagement runs the same checks, in this order:

1. **Not yourself.**
2. **Safe territory.** Federation territory and flagged safe zones are an
   absolute block — they override even a PvP-enabled galaxy.
3. **The galaxy has PvP enabled.**
4. **Same sector, same galaxy.**
5. **The target isn't cloaked** — a cloaked ship reads as simply not there
   unless your effective StarNav is 4 or better.
6. **Not in your corporation.**
7. **The target isn't landed** on their own or their corp's planet.
8. **Neither of you is under PvP immunity.**

Engaging costs **1 turn**.

## The resolution

### Power

Each side computes a power number:

```
raw   = (hullTier × 100) × 0.5
      + 2.0 × fighters      (attack)   or  1.0 × fighters  (defense)
      + 0   × shields       (attack)   or  3.0 × shields   (defense)
      + 5.0 × torpedoes     (attack)   or  0   × torpedoes (defense)

power = raw
      × (role offense/defense + module bonus)
      × region multiplier
      × XP tier multiplier
      × (1 + faction combat bonus)
      × (1 + role combat bonus)
      × ability multiplier
```

Read the weights carefully. **Shields do not attack. Torpedoes do not
defend.** Fighters do both, unevenly. A pure-torpedo ship hits like a truck
and folds like paper.

Modifiers in play:

| Source | Effect |
|---|---|
| Attack Systems module | +10% attack |
| Armor Plating module | +10% defense |
| Combat AI module | +20% fighter effectiveness |
| Faction alignment | +2 / 3 / 4 / 5% at \|alignment\| 500 / 600 / 750 / 900 |
| Fighter role tier | +1% per tier, max +5% |
| XP tier | ×0.95 to ×1.20 by hull tier |
| Region | Federation defenders +10% in `fed_core`, +5% in `fed_space`; attackers +2% in `middle`, +5% in `outer`; pirates +10% in `outer_rim` |
| Hull signature ability | combat / versatility / defense bonuses |

### Win probability

```
winProb = attackerPower / (attackerPower + defenderPower)      each side ×0.98–1.02
        + (attackerFighterShare − 0.5) × 0.30                  fighter skirmish
        + 0.12 stealth first strike (−0.06 vs Advanced Sensors or a sensor-edge hull)
clamped to [5%, 95%]
```

Torpedoes also strip shields out of the defender's power before the ratio is
taken: **1% shield penetration per torpedo, capped at 50%**, reduced by 10%
in an asteroid field.

The 5–95% clamp is real. **You can always lose**, and a hopeless target can
always get lucky one time in twenty.

## Hull and shields

Damage always lands on shields first. Whatever overflows spills into hull at
**×1.5**.

```
shieldLoss = min(shields, damage)
overflow   = damage − shieldLoss
hullLoss   = floor(overflow × 1.5)
```

That multiplier is the design. Fighting on stripped shields is not "a bit
riskier" — every point that gets through costs you one and a half points of
hull, and hull does not come back for free.

Damage is computed against your **whole defense pool** (shields + hull), so a
big hull is not a bystander in the math; it makes the same attrition
percentage into a bigger absolute number.

### Losses

The **winner** loses:

- fighters: `attrition × 40%`
- shield-directed damage: `(shields + hull) × attrition × 25%`
- torpedoes: `20% + 50% × attrition`

The **loser** loses at least **50%**, scaled up by how badly they were
outmatched, applied to fighters, torpedoes and the defense pool. A real fight
always deals at least 1 damage, so a ground-down ship can't asymptote at hull
1 forever.

Both sides' shield loss is reduced by how healthy the shields were going in:
up to a 50% reduction as shields approach 100 points and beyond.

## Escape

Only the **defender** gets an escape roll, and only if the engagement allows
retreat.

```
chance = 0.25
       + 0.35 × your hull's escape rating
       − 0.15 × the attacker's share of total fighters
       + 0.05  in Federation space
       + 0.05–0.08  Corsair-line retreat bonus
       + 0.15  Stealth Plating
       + 0.10  asteroid field
clamped to [5%, 85%]
```

A successful escape means **no losses on either side**. Nothing is looted,
nothing is damaged, no alignment moves.

Pirate hulls carry +0.10 escape over their Federation mirrors, which is worth
+3.5pp on the roll. The Corsair line at 0.60 escape plus its retreat
signature is the slipperiest thing in the game.

## Loot

Only the winner takes anything, and only from a **player** loser (NPCs drop
their own loot table).

| Winner's alignment | Credits | Cargo |
|---|---|---|
| Federation (≥ +300) | 20% | 25% |
| Neutral | 25% | 30% |
| Pirate (≤ −300) | **35%** | **40%** |

The credit take is also capped by the winner's hull tier: 5,000 / 15,000 /
40,000 / 100,000 / 200,000.

**Only the wallet is ever looted. The bank is never touched.**

Cargo loot is taken proportionally across the loser's stacks, and it is
capped by what the winner's holds can actually fit.

## Alignment consequences

| Situation | Attacker wins | Attacker loses |
|---|---|---|
| Attacked a Federation-aligned player | −8 | −3 |
| Attacked a neutral player | −2 | −1 |
| Fought a Pirate-aligned player | +6 | +2 |
| Attacked Federation forces (NPC) | −6 | −2 |
| Attacked a neutral trader (NPC) | −1 | 0 |
| Fought pirate raiders (NPC) | +4 | +1 |

And, separately: **a defender who survives or beats a pirate aggressor earns
+2 alignment** — whether the aggressor was an NPC ambush or another player.
This is one of the few reliable ways a law-abiding trader earns lawful
standing without going hunting. It fires on NPC ambushes, which is the common
case.

Sides are decided by **your alignment**, at ±300 — never by what hull you
fly.

## PvP immunity

One clock, several sources, and it **always extends, never replaces**.

| Source | Duration |
|---|---|
| Losing a fight | 2 minutes |
| **Any death**, from any cause | 2 minutes |
| A purchased defense contract | 2 hours each, stacking |

**Defense contracts cover NPC ambushes too.** This changed in v2.0.2 — a
contract now suppresses pirate and patrol ambushes as well as player attacks,
not just PvP. It is genuine immunity, not just a PvP flag.

Contracts cost **4,000 cr** for **2 hours**, sold where the `defense` service
runs: Federation Ports, the Stardock and the Merchant Exchange. The Pirate
Haven does not sell them.

Three things about immunity that bite people:

1. **You cannot attack while immune.** Immunity is protection, not a free
   swing. Attempting to initiate returns `IMMUNE`.
2. **Immunity is never shortened.** A lost fleet strike used to overwrite
   nearly two hours of purchased contract with a two-minute window. It
   doesn't anymore — every write extends the later of *now* and your current
   window.
3. **Immunity skips warp interruption rolls** entirely.

Immunity also protects you from deployables: limpets cannot latch onto an
immune ship.

## Destruction

Hull 0 is the only death. See
[Ships → Destruction and escape pods](/guide/ships/#destruction-and-escape-pods)
for the full sequence. In short: you lose the ship, everything installed on
it, all its cargo, and **every remaining turn**. You keep your wallet, bank,
XP, alignment and inventory.

## NPC combat

Attacking an NPC checks only *your* immunity — NPCs have none.

NPCs carry no hull pool of their own in the resolver's sense: they die on any
loss. But **damage now sticks to a named NPC between fights** and they
regenerate 25% of their spawn strength per world tick, so a boss you can't
beat outright can be ground down over about four attempts — and will be back
to full roughly sixteen hours later if you leave it alone.

**Losing a fight pays no XP.** That changed in v2.0.8: an unbeatable boss at
1 turn a pull was a steady XP faucet.

Pirates drop 500–2,000 cr scaled by tier. Traders drop 100–500. **Patrols
drop nothing** — killing them only buys you a warrant.

## Fleets

A fleet is up to **three ships** from the **same corporation** operating as
one.

- **Forming** a fleet requires level 15 and corp membership.
- **Joining** requires level 10 and the same corp.
- The leader leaving disbands the fleet.

A **fleet strike** costs 1 turn, is leader-only, and requires every counted
member to be **in the leader's sector with an active ship**. Members
elsewhere contribute nothing.

The strike runs exactly the same gates as solo combat, plus the leader's own
immunity check.

- **Loot goes to the corp bank**, not to the leader's wallet.
- **Attrition is redistributed across members** — everyone bleeds.
- **Any member's hull can reach 0**, and that member goes through the full
  destruction and pod flow.
- Fleet kills now apply the same alignment, statistics and immunity
  consequences as solo kills. The leader personally earns any bounty claims.

## Pending encounters

Not every NPC contact is a fight. A non-aggressive NPC becomes a **pending
encounter** you can act on: bribe, surrender, jettison, submit to a scan,
trade, rob, or engage.

Confirming a fight re-rolls it under the **stored seed**, so the outcome is
deterministic — and confirming does not allow retreat. Walking away means
letting the contact expire.

See [NPCs & Encounters](/guide/npcs/).
