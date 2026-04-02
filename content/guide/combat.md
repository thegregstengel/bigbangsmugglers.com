---
title: "Combat"
date: 2026-04-01
draft: false
description: "Ship combat, PvP zones, combat resolution, and defense strategies"
weight: 4
toc: true
---

Combat in Big Bang Smugglers is fast and automatic. When ships fight, the outcome is determined by their stats and a probabilistic resolution system with no manual inputs during the fight. Win and you loot the loser. Lose and your ship is disabled.

## PvP Zones

Not every sector allows player-vs-player combat.

| Territory | PvP Status |
|-----------|-----------|
| Federation space | Never — safe regardless of galaxy settings |
| Neutral / Unincorporated | Enabled when galaxy PvP is on |
| Pirate space | Enabled when galaxy PvP is on |

All ports are safe havens. Docked ships cannot attack or be attacked in any sector.

The territory badge on the Nav screen shows your current status. A shield icon means safe. A sword icon means PvP is enabled in this sector.

## Initiating Combat

To attack a player: be in the same pirate or neutral sector with PvP enabled, both ships undocked and not disabled, and neither under PvP immunity. Tap the players indicator, select your target, and tap Attack.

The attacker spends 1 turn. Defenders use no turns.

## Combat Resolution

Combat is automatic. Here is how it works.

### Power Calculation

```
rawPower = basePower + (fighters × 0.8) + (shields × 1.2) + (torpedoes × 2.0)
effectivePower = rawPower × roleMultiplier × regionMultiplier × xpMultiplier
winProbability = attackerPower / (attackerPower + defenderPower)
```

**Note:** The base formula structure above is correct, but the underlying weights were significantly rebalanced in v1.8.0. Ship base power dominance was reduced, and fighter, torpedo, and shield contributions were all increased. Ships that are loaded with consumables and upgraded stat lines now outperform ships that rely on base tier alone.

### Pre-Roll Mechanics (v1.8.0+)

Before the main combat roll, two additional effects resolve:

- **Fighter superiority:** If one side has a significantly higher fighter count, this shifts win odds before the main power comparison.
- **Shield attrition reduction:** Higher shield values reduce incoming damage, giving shielded ships more staying power across the combat calculation.
- **Torpedo shield penetration:** Torpedoes partially bypass shields, making them effective against heavily-shielded targets.

### Random Factor

A small random factor applies to each side's power before resolution. This prevents fully deterministic outcomes — an underdog can win, but the stronger ship wins more often.

### Environmental Modifiers

Sector conditions can affect combat outcomes. Nebulae, asteroid fields, and other environmental hazards may shift effective power for one or both sides depending on ship configuration.

### Region Bonuses

Federation-aligned ships defending in Federation Core get a 10% defense bonus. In Federation Space it is 5%.

---

## Loot and Consequences

**If the attacker wins:**

- Credits looted: up to 25% of the defender's credits, capped by the winner's ship tier
- Cargo looted: up to 30% of the defender's cargo hold contents
- Defender ship: disabled for roughly 2 minutes, then auto-repaired to 50% capacity
- Defender receives 2 minutes of PvP immunity after recovery

If the defender wins, the same loot logic applies in reverse.

**Credit caps by ship tier:**

| Tier | Credit Cap |
|------|-----------|
| 1–2 | 5,000 cr |
| 3 | 15,000 cr |
| 4 | 40,000 cr |
| 5 | 100,000 cr |

### Alignment Effects

Attacking players shifts your alignment toward Pirate. Magnitude depends on combat context.

---

## PvP Immunity

After being disabled in combat, your ship has 2 minutes of PvP immunity. You cannot be attacked and cannot initiate attacks. This prevents spawn-camping.

---

## NPC Combat

The same resolution system applies to NPC encounters. See [NPCs & Encounters](/guide/npcs) for interaction options before combat resolves. You can attempt to retreat from NPC combat with success based on your escape stat. NPC loot is credits plus commodity cargo that varies by NPC type and region.

---

## Assessing Targets

When you open an NPC encounter, the modal shows your attack power versus the enemy's combat power before you commit. Win odds labels:

| Label | Win Chance |
|-------|-----------|
| Heavily Favored | 75%+ |
| Favored | 60–74% |
| Even Odds | 45–59% |
| Risky | 30–44% |
| Dangerous | Below 30% |

You can always choose not to engage.

---

## Combat Recap Screen

After every combat, a recap screen shows both sides' stats side by side: fighters, shields, torpedoes, calculated combat power, and win probability going in. Losses, loot, and any bounty collected appear in the outcome section. If your ship was disabled the recap shows the auto-repair timing.

---

## Upgrading for Combat

**Tech Hub upgrades:**

- Shield Booster Arrays — 10,000 cr — +15% max shields permanently
- Combat AI Core — 15,000 cr — +20% fighter effectiveness permanently
- Advanced Attack Systems — 22,000 cr, 6,000 XP required — +10% offense multiplier
- Reinforced Armor Plating — 22,000 cr, 6,000 XP required — +10% defense multiplier
- Emergency Escape Pods — 12,000 cr — +15% escape chance from NPC combat

Restock fighters and torpedoes at any starport between fights.

### XP Tier Bonus

Your XP tier applies a multiplier to effective combat power. Each tier above 1 adds 4%, up to 16% at Tier 5. A Tier 5 veteran fighting an identical Tier 1 ship has a meaningful edge in close fights.

### Combat Power Display

Your Ship screen shows current Attack Power and Defense Power using the same formula the backend uses.

---

## Ship Disable and Recovery

When disabled you cannot move or take most actions. Your ship auto-repairs to 50% capacity at the next daily reset. You can manually repair at any starport for full restoration at a credit cost. If disabled in a dangerous sector, dock at a nearby port to prevent further attacks while you recover.

---

## Feed Notifications

Three feed messages are created per combat event: one private to the attacker with loot details, one private to the defender with losses, and one public showing who defeated whom. Popup alerts fire instantly for combat involving your ship.
