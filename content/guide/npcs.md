---
title: "NPCs & Encounters"
date: 2026-04-01
draft: false
description: "NPC ships, encounter interactions, and territory behavior"
weight: 5
toc: true
---

The galaxy has NPCs moving through it at all times. Federation patrols enforce the law, pirates hunt for prey, and traders run commodity routes. Each type behaves differently and presents different interaction options when you encounter them.

## How Encounters Work

Every sector move rolls for an NPC encounter. At most one NPC spawns per move. Encounter probability depends on your current region, the NPC type, and the galaxy's base encounter rate. NPCs are visible in sectors on the Nav screen before you interact with them.

When an encounter fires, you see an engagement modal. Each NPC type shows different options. Unlike earlier versions of the game, most encounters are not automatic — you choose how to respond.

---

## NPC Types

### Federation Patrols

Patrols enforce Federation law. They scan cargo and enforce faction standing. They are not automatically aggressive unless you have an active bounty.

**Encounter options:**

- **Scan** — let them scan your cargo (safe if you're clean)
- **Bribe** — pay credits to avoid the scan
- **Jettison** — dump your contraband before they check
- **Attack** — engage the patrol in combat (generates a faction bounty)

**Territory behavior:**

- Heavy presence in Federation Core and Federation Space
- Reduced in Frontier regions
- Do not spawn in Pirate or Deep space

**Aggression:** Patrols only initiate combat if you have an active bounty. Otherwise they scan and move on.

---

### Pirates

Pirate ships attack for cargo and credits. They range from tier 2 Raider Skiffs through tier 5 Warlord Battleships, with higher tiers in deeper space.

**Encounter options:**

- **Surrender** — let them take cargo and credits without fighting
- **Bribe** — pay to be left alone
- **Jettison** — dump cargo to reduce what they take
- **Attack** — fight back

Bounty hunters (players with pirate bounties on them) face a more hostile interaction path with fewer options.

**Territory behavior:**

- Do not spawn in Federation space
- Concentrate in Frontier, Pirate, and Deep regions
- More frequent and higher tier in Deep space

**Loot from defeating pirates:** 500 to 2,000 credits plus equipment cargo. Deep space pirates drop more.

---

### Traders

Civilian merchant ships running commodity routes. They carry cargo and modest credits but are never automatically hostile.

**Encounter options:**

- **Trade** — buy or sell commodities with the NPC at current prices
- **Rob** — attack and take their cargo
- **Attack** — engage in combat without a trade offer

Traders never auto-popup. Interactions are always player-initiated.

**Territory behavior:**

- Concentrated in Federation Core, Federation Space, and Frontier regions
- Rare in Pirate or Deep space

**Loot from defeating traders:** 100 to 500 credits plus mixed commodity cargo.

---

## Territory Summary

| Territory | Pirates | Patrols | Traders |
|-----------|---------|---------|---------|
| Federation Core | None | Heavy | Frequent |
| Federation Space | None | Heavy | Frequent |
| Frontier | Moderate | Light | Moderate |
| Neutral | Moderate | Light | Moderate |
| Pirate | Heavy | None | Rare |
| Deep | Heavy | None | Very rare |

---

## Faction Reputation and NPC Memory

NPCs respond to your faction history. Attacking Federation-aligned NPCs degrades your Federation reputation and generates faction bounties. Attacking Pirate-aligned NPCs does the same on the pirate side. Faction memory makes the galaxy more reactive over time — a reputation for piracy changes how patrols treat you, and a bounty on your head makes every patrol encounter hostile.

See [Bounties](/guide/bounties) for how faction bounties are generated and collected.

---

## NPC Combat

When you choose to fight — or when an NPC attacks first — combat resolves automatically using the same formula as PvP. See [Combat](/guide/combat) for the full resolution system.

NPC tiers scale with region danger. Be aware of win odds before engaging deep-space targets.
