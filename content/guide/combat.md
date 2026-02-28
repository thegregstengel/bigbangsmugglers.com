---
title: "Combat"
date: 2026-02-28
draft: false
description: "Ship combat, PvP zones, combat resolution, and defense strategies"
weight: 4
toc: true
---

Combat in Big Bang Smugglers is fast, automatic, and permanent. When ships fight, the outcome is determined by their stats and a probabilistic resolution system — no manual inputs, no turns. Win and you loot the loser. Lose and your ship is disabled.

## PvP Zones

Not every sector allows player-vs-player combat.

| Territory | PvP Status |
|-----------|-----------|
| Federation space | **Never** — always safe regardless of galaxy settings |
| Neutral / Unincorporated | Enabled when galaxy PvP is on |
| Pirate space | Enabled when galaxy PvP is on |

**All ports are safe havens.** Docked ships cannot attack or be attacked, in any sector.

The **territory badge** on the Nav screen shows your current status:
- 🛡️ **Shield icon** — safe zone, no PvP
- ⚔️ **Sword icon** — PvP enabled in this sector

## Initiating Combat

**To attack a player:**
1. Be in the same sector (pirate or neutral, PvP enabled)
2. Both ships must be undocked and not disabled
3. Neither ship can be under PvP immunity
4. Tap the players indicator → select target → Attack

**Turn cost:** 1 turn for the attacker. Defenders use no turns.

**Requirements checklist:**
- Galaxy PvP must be enabled
- Sector must be pirate or neutral territory
- You must have at least 1 turn remaining
- Target must be in your sector, undocked, not disabled, not immune

## Combat Resolution

Combat is automatic — no manual moves. Here's how the system works:

### Power Calculation

Each ship's effective combat power is:

```
rawPower = basePower + (fighters × 0.8) + (shields × 1.2) + (torpedoes × 2.0)
effectivePower = rawPower × roleMultiplier × regionMultiplier × xpMultiplier
```

**Shields are the most cost-effective** stat per point (coefficient 1.2). Torpedoes hit hardest individually (coefficient 2.0). Fighters provide solid base power (0.8) and are cheapest to restock.

### Random Factor

A small random "drizzle" is applied to each side's power before resolution. This prevents combat from being purely deterministic — an underdog can win, but the stronger ship wins more often.

### Win Probability

```
winProbability = attackerPower / (attackerPower + defenderPower)
```

A ship with double the effective power wins roughly 67% of the time.

### Region Bonuses

- **Federation Core / Federation Space:** +5–10% defense bonus for Federation-aligned ships defending
- **Frontier space:** Small attacker bonus
- Pirate and deep space: Standard rates

## Loot & Consequences

### If the Attacker Wins
- **Credits looted:** Up to 25% of the defender's credits, capped by the winner's ship tier (e.g. tier 2 caps at 5,000 cr, tier 5 caps at 200,000 cr)
- **Cargo looted:** Up to 30% of the defender's cargo hold contents
- **Defender ship:** Disabled for ~2 minutes, then auto-repaired to 50% capacity
- **Defender gets:** 2-minute PvP immunity after recovery

### If the Defender Wins
- Same loot logic applies (defender loots attacker)
- Attacker ship disabled

### Alignment Effects
- Attacking players shifts your alignment toward Pirate
- Defending and winning is neutral
- The magnitude depends on combat context

## PvP Immunity

After being disabled in combat, your ship has **2 minutes of PvP immunity**. During immunity:
- You cannot be attacked
- You cannot initiate attacks

This prevents spawn-camping.

## NPC Combat

The same resolution system applies to NPC encounters. Key differences:
- NPCs may auto-aggress based on territory (see [NPCs & Encounters](/guide/npcs))
- You can retreat from NPC combat if `allowRetreat` is set — success chance based on your escape stat
- NPC loot is credits + commodity cargo (amounts vary by NPC type and region)

## Combat Notifications

Three feed messages are created per combat event:
- **Private to attacker:** "You attacked [player] and won/lost. [Loot details]"
- **Private to defender:** "You were attacked by [player] and won/lost. [Loot details]"
- **Public galaxy feed:** "[Attacker] defeated [Defender]" (minor severity)

The global combat listener in-app shows instant popup alerts for combat involving you.

## Upgrading for Combat

**Best combat investments:**
- **Shield Booster Arrays** (Tech Hub, 10,000 cr) — +15% max shields, permanent
- **Combat AI Core** (Tech Hub, 15,000 cr) — +20% fighter effectiveness, permanent
- Restock fighters at any starport between fights
- Restock torpedoes at any starport

**Escape-focused:**
- **Emergency Escape Pods** (Tech Hub, 12,000 cr) — +15% escape chance from NPC combat

## Ship Disable & Recovery

When your ship is disabled:
- You cannot move or take most actions
- Your ship auto-repairs to **50% capacity** at the next daily reset
- You can also manually repair at a starport for full restoration (costs credits)

If you're in a dangerous sector when disabled, dock at a nearby port to avoid being looted again while recovering.
