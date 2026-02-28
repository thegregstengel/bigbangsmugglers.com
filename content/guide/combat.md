---
title: "Combat"
date: 2026-02-28
draft: false
description: "Ship combat, PvP zones, combat resolution, and defense strategies"
weight: 4
toc: true
---

Combat in Big Bang Smugglers is fast and automatic. When ships fight, the outcome is determined by their stats and a probabilistic resolution system with no manual inputs. Win and you loot the loser. Lose and your ship is disabled.

## PvP Zones

Not every sector allows player-vs-player combat.

| Territory | PvP Status |
|-----------|-----------|
| Federation space | Never, always safe regardless of galaxy settings |
| Neutral / Unincorporated | Enabled when galaxy PvP is on |
| Pirate space | Enabled when galaxy PvP is on |

All ports are safe havens. Docked ships cannot attack or be attacked in any sector.

The territory badge on the Nav screen shows your current status. A shield icon means safe. A sword icon means PvP is enabled in this sector.

## Initiating Combat

To attack a player you need to be in the same pirate or neutral sector with PvP enabled, both ships must be undocked and not disabled, and neither ship can be under PvP immunity. Tap the players indicator, select your target, and tap Attack.

The attacker spends 1 turn. Defenders use no turns.

## Combat Resolution

Combat is automatic. Here is how it works.

### Power Calculation

Each ship's effective combat power is:

```
rawPower = basePower + (fighters × 0.8) + (shields × 1.2) + (torpedoes × 2.0)
effectivePower = rawPower × roleMultiplier × regionMultiplier × xpMultiplier
winProbability = attackerPower / (attackerPower + defenderPower)
```

Shields are the most cost-effective stat per point. Torpedoes hit hardest individually. Fighters provide solid base power and are cheapest to restock.

### Random Factor

A small random factor is applied to each side's power before resolution. This prevents combat from being purely deterministic. An underdog can win, but the stronger ship wins more often.

### Region Bonuses

Federation-aligned ships defending in Federation Core get a 10% defense bonus. In Federation Space it is 5%.

## Loot and Consequences

**If the attacker wins:**

- Credits looted: up to 25% of the defender's credits, capped by the winner's ship tier (tier 2 caps at 5,000 cr, tier 5 caps at 200,000 cr)
- Cargo looted: up to 30% of the defender's cargo hold contents
- Defender ship: disabled for roughly 2 minutes, then auto-repaired to 50% capacity
- Defender receives 2 minutes of PvP immunity after recovery

If the defender wins, the same loot logic applies in reverse.

### Alignment Effects

Attacking players shifts your alignment toward Pirate. The magnitude depends on combat context.

## PvP Immunity

After being disabled in combat, your ship has 2 minutes of PvP immunity. During immunity you cannot be attacked and cannot initiate attacks. This prevents spawn-camping.

## NPC Combat

The same resolution system applies to NPC encounters. NPCs may auto-aggress based on territory (see [NPCs & Encounters](/guide/npcs)). You can attempt to retreat from NPC combat with success based on your escape stat. NPC loot is credits plus commodity cargo that varies by NPC type and region.

## Combat Notifications

Three feed messages are created per combat event. One is private to the attacker with loot details. One is private to the defender with what was lost. One is public to the galaxy feed showing who defeated whom. The global combat listener in the app shows instant popup alerts for combat involving you.

## Combat Recap Screen

After every combat resolves, a recap screen shows both sides' stats before and after the fight. The layout shows each ship's fighters, shields, torpedoes, and calculated combat power side by side, along with your win probability going in. Losses, loot, and any bounty collected are shown in the outcome section. If your ship was disabled the recap notes the auto-repair timing.

## Assessing NPC Targets

When you open an NPC encounter, the modal shows your attack power versus the enemy's combat power before you decide to engage. A win odds label summarizes the matchup: Heavily Favored means 75% or higher, Favored is 60 to 74%, Even Odds is 45 to 59%, Risky is 30 to 44%, and Dangerous is below 30%. You can always choose not to engage.

## Upgrading for Combat

**Tech Hub upgrades for combat:**

- Shield Booster Arrays, 10,000 cr, adds 15% max shields permanently
- Combat AI Core, 15,000 cr, adds 20% fighter effectiveness permanently
- Advanced Attack Systems, 22,000 cr / 6,000 XP required, +10% offense multiplier in combat
- Reinforced Armor Plating, 22,000 cr / 6,000 XP required, +10% defense multiplier in combat
- Emergency Escape Pods, 12,000 cr, adds 15% escape chance from NPC combat

Restock fighters and torpedoes at any starport between fights.

### XP Tier Bonus

Your XP tier applies a multiplier to your effective combat power. Each tier above 1 adds 4% to your power, up to a maximum of 16% at Tier 5. A Tier 5 veteran fighting an identical Tier 1 ship has a meaningful edge in close fights.

### Combat Power Display

Your Ship screen shows your current Attack Power and Defense Power at a glance. The formula applied is the same one the backend uses, so the number you see is the number used in actual combat.

## Ship Disable and Recovery

When your ship is disabled you cannot move or take most actions. Your ship auto-repairs to 50% capacity at the next daily reset. You can also manually repair at a starport for full restoration at a credit cost. If you are in a dangerous sector when disabled, docking at a nearby port prevents further attacks while you recover.
