---
title: "NPCs & Encounters"
date: 2026-07-02
draft: false
description: "NPC ships, encounter odds, interaction options, and loot"
weight: 8
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

The galaxy has NPCs moving through it at all times. Federation patrols enforce the law, pirates hunt for prey, and traders run commodity routes. Each type behaves differently and presents different options when you encounter it.

## How Encounters Work

Every sector move rolls once for an NPC encounter — at most one NPC spawns per move. Warp hops roll too (see Warp Encounters below). The base chance per move is **3% for pirates, 2% for traders, and 1.5% for patrols**, multiplied by where you are:

| Region | Pirates | Traders | Patrols |
|--------|---------|---------|---------|
| Federation Core | 0 | ×1.5 | ×4.0 |
| Federation Space | 0 | ×1.5 | ×3.5 |
| Inner Systems | ×0.4 | ×1.8 | ×1.5 |
| Middle Band | ×1.0 | ×2.0 | ×0.8 |
| Outer Reaches | ×1.5 | ×0.5 | ×0.1 |
| Outer Rim | ×2.0 | ×0.3 | 0 |

Note the trader hotspot is the **Middle Band**, not Federation space — mid-galaxy is where the commodity routes run.

On top of the region multipliers, **territory** applies hard blocks: pirates never spawn in Federation territory, and patrols never spawn in pirate territory, period. Sectors also have density caps — at most 2 active patrols and 3 active pirates per sector (traders are uncapped). Once a cap is hit, no more of that type spawn there.

## Combat Is Decided When You Move

NPC combat uses an **instant-resolution model**: the fight's outcome is computed the moment the encounter fires, during your move.

- **Ambushes** (auto-aggressive NPCs): the combat result is committed before you see anything. The modal shows you a recap — you cannot flee an ambush.
- **Non-aggressive encounters:** the result is pre-rolled and stored. Tapping **Attack** reveals and applies it; **fleeing costs nothing** — no roll, no penalty, no turn.
- A committed fight costs **1 turn** on top of the move that triggered it. All diplomacy options (scan, bribe, surrender, jettison, trade, rob) cost **0 turns**.

You choose *how to respond* — diplomacy or violence — but once you commit to the fight, the dice were already thrown.

## Seeing NPCs

NPCs are visible in the sector list on the Nav screen with an **Engage** button, so you can size them up (or ignore them) before acting. The exception is a freshly spawned pirate or patrol encounter, which interrupts you with a **blocking modal** — there is no Leave button; you must pick an option. Traders never interrupt: they appear silently in the sector list and every trader interaction is player-initiated. Any NPC lingering in a sector can simply be ignored — move on.

---

## NPC Types

### Federation Patrols

Patrols enforce Federation law. They scan cargo and are never aggressive at spawn — **unless you carry an active Federation bounty, in which case they attack on sight** with no options offered.

**Encounter options:**

| Option | What happens |
|--------|--------------|
| **Allow Scan** | Clean: **+2 alignment**. Caught: all contraband seized, **−5 alignment**. |
| **Bribe** | Cost by patrol tier (table below). **60% success** (+15% if your alignment is below −300). Success: patrol leaves, −1 alignment. Failure: credits lost, **−2 alignment, and the scan runs anyway** — if it catches contraband, add the seizure, −5 alignment, and a **2,000 cr fine**. |
| **Jettison Contraband** | Dumps ALL your contraband. Free, no penalty, always works. |
| **Attack** | Fight. Winning puts a **Federation bounty on your head**. |

**Territory behavior:** heavy in Federation Core and Federation Space, moderate in the Inner Systems, thin in the Middle Band, nearly absent in the Outer Reaches, and never in the Outer Rim or pirate territory.

**Patrol ships:**

| Tier | Class | Fighters | Shields | Torpedoes |
|------|-------|----------|---------|-----------|
| 2 | Fed Patrol Cutter | 30–60 | 40–80 | 10–25 |
| 3 | Federation Frigate | 60–140 | 80–180 | 15–40 |
| 4 | Federation Cruiser | 140–300 | 180–350 | 30–60 |
| 5 | Star Defender | 300–550 | 350–600 | 50–90 |

The heaviest patrols (tiers 4–5) fly in Federation Core; the frontier gets cutters and frigates.

**Patrols drop nothing.** Zero credits, zero cargo. Killing one shifts your alignment −6, raises your pirate reputation (+15 × tier), and generates a Federation bounty on you — it is a faction-politics play, never a profit play.

---

### Pirates

Pirate ships hunt cargo and credits. Whether a pirate ambushes you on sight depends on your alignment and where you are:

| Your alignment | Pirate territory | Neutral space |
|----------------|------------------|---------------|
| Pirate-aligned (below −300) | Never attacked | Never attacked |
| Neutral | 66% | 33% |
| Federation-aligned (above +300) | 100% | 66% |

An active **pirate bounty** on you overrides everything: pirates attack on sight, hunting the payout.

**Encounter options** (non-aggressive pirates):

| Option | What happens |
|--------|--------------|
| **Surrender Cargo** | The pirate takes **30% of your cargo units**. If your holds are empty, it takes **10% of your wallet, capped at 5,000 cr** — never both. No fight, no alignment change. |
| **Bribe** | Cost by pirate tier (table below). **65% success** (+15% if your alignment is below −300, capped 95%). The credits are **lost even on failure** — and a failed bribe forces immediate combat with no escape. |
| **Jettison Cargo** | Dumps **25% of your cargo** (cheapest lots first) as a distraction. **Always works** — a guaranteed escape priced at a quarter of your hold. |
| **Fight** | Combat. Winning shifts alignment +4, pays Federation reputation (+15 × tier), and generates a **pirate syndicate bounty on you**. |

**Bribe costs** (identical for pirates and patrols):

| NPC tier | Bribe cost |
|----------|-----------|
| 1 | 500 cr |
| 2 | 1,500 cr |
| 3 | 4,000 cr |
| 4 | 10,000 cr |
| 5 | 25,000 cr |

**Territory behavior:** never in Federation space; density climbs from the Inner Systems outward, peaking in the Outer Rim, where the biggest hulls fly.

**Pirate ships:**

| Tier | Class | Fighters | Shields | Torpedoes |
|------|-------|----------|---------|-----------|
| 2 | Raider Skiff | 20–50 | 15–40 | 5–15 |
| 3 | Smuggler Corvette | 50–120 | 40–100 | 10–30 |
| 4 | Marauder Cruiser | 120–250 | 100–200 | 20–50 |
| 5 | Warlord Battleship | 250–500 | 200–400 | 40–80 |

Inner Systems pirates run tiers 2–3; the Outer Rim fields tiers 3–5.

**Loot from defeating pirates:** 500–2,000 cr base plus cargo (equipment-heavy), scaled by the tier multiplier below. Outer Rim pirates use a richer table: 1,000–4,000 cr with bigger cargo drops.

---

### Traders

Civilian merchant ships running commodity routes. They spawn silently — no popup, ever — and are never hostile. Engage them from the sector list.

**Encounter options:**

| Option | What happens |
|--------|--------------|
| **Trade** | Buy and sell at **fixed convenience prices** — never linked to port markets. Buy: fuel 30 / organics 45 / equipment 75 cr. Sell: fuel 13 / organics 20 / equipment 33 cr (all before reputation adjustment). Each transaction earns **+1 trader reputation**. |
| **Rob** | **Always succeeds** — traders don't fight. Loot by tier (table below). Costs **−2 alignment and −3 trader reputation**. |
| **Attack** | Full combat. Killing a trader costs **−5 trader reputation**. |

**Rob loot by trader tier:**

| Tier | Credits | Cargo units |
|------|---------|-------------|
| 1 | 50–200 | 1–5 |
| 2 | 150–500 | 3–10 |
| 3 | 400–1,500 | 5–20 |
| 4 | 1,000–4,000 | 10–35 |
| 5 | 2,500–10,000 | 15–50 |

**Territory behavior:** everywhere lawful, densest in the Middle Band and Inner Systems, sparse in the Outer Reaches and Outer Rim.

**Trader ships:**

| Tier | Class | Fighters | Shields | Torpedoes |
|------|-------|----------|---------|-----------|
| 1 | Merchant Shuttle | 5–15 | 10–30 | 0–5 |
| 2 | Cargo Hauler | 15–40 | 30–70 | 0–10 |
| 3 | Star Trader | 40–90 | 70–150 | 5–20 |

**Loot from killing traders in combat:** 100–500 cr base (200–800 in the Middle Band) plus mixed commodity cargo, scaled by tier.

---

## Loot Summary

All kill loot is a base roll from the tables above multiplied by the NPC's tier:

| NPC tier | Loot multiplier |
|----------|----------------|
| 1 | ×0.75 |
| 2 | ×1.0 |
| 3 | ×1.25 |
| 4 | ×1.5 |
| 5 | ×1.75 |

| Type | Credits (base) | Cargo | Worth fighting for profit? |
|------|----------------|-------|---------------------------|
| Pirates | 500–2,000 (Outer Rim: 1,000–4,000) | Yes, equipment-heavy | Yes |
| Traders | 100–500 (Middle Band: 200–800) | Yes, mixed commodities | Yes, at a reputation price |
| Patrols | **0** | **None** | Never — rep and bounty consequences only |

---

## How NPCs React to You

NPC reactivity comes entirely from **alignment thresholds and active bounties** — NPCs do not remember individual past interactions.

- **Below −300 alignment:** pirates never ambush you, and your bribes get +15% success with both pirates and patrols.
- **Above +300 alignment:** pirates ambush you more (66% in neutral space, always in pirate territory), but contraband scans skip you entirely.
- **Active Federation bounty:** patrols attack on sight.
- **Active pirate bounty:** pirates attack on sight.

That's the whole list. There is no long-term grudge system — a patrol you bribed yesterday treats you exactly like one you've never met. See [Bounties](/guide/bounties/) for how faction bounties are generated and collected, and [Reputation & Factions](/guide/reputation-factions/) for the alignment ladder.

---

## NPC Lifecycle

NPCs are transient. Each one despawns about **2 hours** after spawning, and every 4-hour cycle a surviving NPC has a 20% chance to wander to an adjacent sector. NPCs are visible to every player in the sector, and defeating one removes it for everyone.

NPCs carry randomized display names — "Black Marauder", "FSS Justice" — with the ship class shown separately. One naming trap: the tier-5 pirate NPC is a **Warlord Battleship**, while the player-purchasable pirate tier-3 raider is named **Warlord**. Different ships.

---

## Warp Encounters

Warp hops roll for encounters too, with the total interruption chance over any journey capped at roughly **30%**. Any NPC halts your warp at that hop (unused turns refunded); only an auto-aggressive pirate forces combat, committed before you see it. One quirk worth knowing: warp encounter rolls treat every player as neutral — your alignment and any bounties on you are ignored mid-warp, so pirate-aligned players lose their ambush immunity while warping.

---

## NPC Combat

When a fight commits, it resolves automatically with the same formula as PvP — see [Combat](/guide/combat/) for the full system, including the win-odds labels. NPCs never retreat or escape; and when you are the one attacking, neither do you. NPC tiers scale with region danger, so check the odds label before engaging deep-space targets — and treat the modal's power preview as rough guidance, since the server's pre-rolled result is what actually stands.
