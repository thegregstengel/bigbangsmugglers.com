---
title: "NPCs & Encounters"
date: 2026-02-28
draft: false
description: "NPC ships, encounter rates, and territory aggression"
weight: 5
toc: true
---

The galaxy is not empty. As you move between sectors, you'll encounter NPC ships - pirates looking for prey, traders running their routes, and Federation patrols enforcing the law.

## How Encounters Work

Every time you move to a new sector, the game rolls for an NPC encounter. At most **one NPC spawns per move**. The probability depends on:

- Your current region (CORE, OUTER, PIRATE, etc.)
- The type of NPC
- The galaxy's base encounter rate setting

## NPC Types

### Pirate Ships

The most dangerous encounter. Pirates are found throughout the galaxy but concentrate heavily in outer and deep space.

**Aggression by territory:**
- **Federation space:** Never attacks first (0%)
- **Neutral/Unincorporated space:** 33% chance of auto-attacking on spawn
- **Pirate space:** 66% chance of auto-attacking on spawn

**Spawn rates by region** (relative, higher = more common):
- Pirate space: 2x base rate
- Outer rim: 1.5x
- Frontier: 1.2x
- Deep space: 1.3x
- Fed core: 0.2x (very rare)

**Loot from defeating pirates:** 500–2,000 credits + equipment cargo. Deep space pirates drop more.

**Tiers:** Pirate ships range from tier 2 (Raider Skiff) to tier 5 (Warlord Battleship). Higher tiers appear in deeper, more dangerous regions.

### Federation Patrols

Patrol ships enforce Federation law. They do **not** attack players on sight - they exist to scan for contraband.

- Patrols **never auto-aggress** regardless of territory
- When a patrol is present in a sector you move into, it scans your cargo if you're in Federation or neutral space
- Carrying contraband triggers the detection roll (see [Smuggling Guide](/guide/smuggling))

**Spawn rates:** Patrol ships concentrate heavily in Federation core and Federation space regions, with reduced presence in frontier and outer zones. They almost never appear in deep space or pirate territory.

**Tiers:** Fed Patrol Cutter (tier 2) through Star Defender (tier 5).

### Traders

Civilian merchant ships running trade routes. Generally non-threatening.

- Traders never auto-aggress
- They carry cargo and modest credits if defeated in PvP zones
- Concentrated in core, inner, and Federation regions
- Rare in pirate or deep space

**Loot from defeating traders:** 100–500 credits + mixed commodity cargo (fuel, organics, equipment).

## Territory & Safety

The territory type of a sector directly affects how dangerous it is:

| Territory | Pirate Aggression | Patrol Presence | Contraband Risk |
|-----------|-------------------|-----------------|-----------------|
| Federation | 0% | High | Active scanning |
| Neutral/Unincorporated | 33% | Low | Active scanning |
| Pirate | 66% | Minimal | No scanning |

**Federation space** is the safest for travel but actively hostile to smugglers. **Pirate space** is the most dangerous for combat but completely permissive for contraband.

## NPC Combat

When an NPC auto-aggresses, combat resolves automatically using your ship's stats vs. the NPC's stats. You'll see the result as an encounter notification.

- **Win:** Loot the NPC for credits and cargo
- **Lose:** Your ship is disabled, cargo may be lost

NPC combat uses the same resolution system as PvP combat. Upgrade your fighters, shields, and torpedoes to handle tougher encounters in dangerous regions.
