---
title: "PvP System Overhaul - Sector-Based Combat with Safe Zones"
date: 2026-02-14
description: "PvP moved from ports to sectors with faction-based safety rules"
author: "Dev Team"
---

## The Problem

PvP combat was broken in subtle ways:

1. **Wrong Location:** Battle station was a port service (why would space combat require a port?)
2. **Not Enforced:** The `pvpEnabled` flag was cosmetic - didn't actually disable PvP
3. **No Safe Zones:** New players had no protection, spawned into potential combat immediately

The result? Confusion, frustration, and PvP that felt tacked-on rather than integrated.

## The Vision

**PvP should be sector-based, not port-based.** You're in space - combat happens anywhere, anytime (when allowed).

**Federation space should be a permanent safe zone.** New players need protection. Veterans need sanctuary.

**The rules should be clear and predictable.** No surprises. You know if you're in danger.

## The Solution: Faction-Based Safety

### PvP Zone Logic

| Sector Faction | pvpEnabled: false | pvpEnabled: true |
|----------------|-------------------|------------------|
| Federation     | ❌ No PvP         | ❌ No PvP (always safe) |
| Pirate         | ❌ No PvP         | ✅ PvP Allowed |
| Neutral        | ❌ No PvP         | ✅ PvP Allowed |

**Simple Rules:**
- **Federation = Always Safe** (permanent safe zone)
- **Pirate/Neutral = PvP when galaxy enables it**

### Port Safety

Docked players **cannot attack** and **cannot be attacked** (everywhere, all factions).

Ports are safe havens - manage inventory, repair, upgrade without fear.

### Turn Requirements

- Attacker must have **≥1 turn** to initiate combat
- 0 turns = cannot attack
- Defender does **not** lose turns (didn't choose combat)
- Moving to escape costs 1 turn (standard move)

## Implementation: Phase 1

### Backend Enforcement

**Added to `combatInitiateV1.ts`:**

```typescript
// Step 1: Check galaxy pvpEnabled
const pvpEnabled = galaxyData.config?.combat?.pvpEnabled ?? true;

// Step 2: Check sector faction
const sectorFaction = sectorDoc.data()?.faction; // 'federation' | 'pirate' | null

// Step 3: Enforce rules
if (sectorFaction === 'federation') {
  return { error: "PvP is disabled in Federation space" };
}
if (!pvpEnabled) {
  return { error: "PvP is disabled in this galaxy" };
}
```

**Result:** PvP flag now actually works

### UI Redesign

**Removed battle station from ports** - PvP is no longer a port service

**Added to NavScreen:**
- **Zone Badges:** 🛡️ Safe Zone (Federation) / ⚔️ PvP Zone (Pirate/Neutral)
- **Players Indicator:** "⚔️ 3 players in sector - Tap to engage"
- **BattleStationModal:** Sector-based combat modal (not port-based)

**Visual Feedback:**
- Green badges for safe zones
- Red badges for PvP zones
- Indicator only shows in PvP-enabled sectors

### Old UI Deleted

- `BattleStationSubScreen.tsx` (port version - 389 lines)
- `CombatScreen.tsx` (orphaned code - 648 lines)

**Net:** -570 lines removed

## How It Works Now

### In Federation Space

```
Enter Federation sector
  ↓
Zone badge: 🛡️ Safe Zone (green)
  ↓
No players indicator (even if others present)
  ↓
Backend blocks combat attempts
```

### In Pirate/Neutral Space (pvpEnabled: true)

```
Enter Pirate sector
  ↓
Zone badge: ⚔️ PvP Zone (red)
  ↓
Players indicator: ⚔️ 2 players in sector
  ↓
Tap indicator → BattleStationModal
  ↓
Select target → Combat initiates
  ↓
Results shown → Feed notification posted
```

### At Any Port (Docked)

```
Dock at port
  ↓
Cannot attack others
  ↓
Cannot be attacked by others
  ↓
Safe to manage inventory, repair, upgrade
```

## Combat Flow

### 1. Detection
- Other players in sector? Indicator shows (if PvP allowed)
- Tap indicator → BattleStationModal opens

### 2. Target Selection
- Modal shows all players in sector
- Displays name, ship class, alignment
- Attack button per player

### 3. Initiation
- Costs 1 turn
- Backend validates: turns, docking, sector, faction, pvpEnabled
- If valid, combat proceeds

### 4. Resolution
- Combat resolved immediately (CombatResolver unchanged)
- Winner/loser determined
- XP, loot, reputation, alignment effects applied

### 5. Results
- Alert shown with combat summary
- Feed notification posted
- Player list refreshed

## Error Messages

Clear, user-friendly feedback:

- **"PvP is disabled in Federation space"** - You're in a safe zone
- **"PvP is disabled in this galaxy"** - Galaxy admin disabled PvP
- **"Cannot attack while docked"** - Undock first
- **"Cannot attack a docked ship"** - Target is protected
- **"No turns remaining"** - Wait for turn refresh

## Statistics

**Code Changes:**
- Backend: +40 lines (enforcement)
- Frontend: +498 lines (BattleStationModal, indicators, badges)
- Deleted: -1,068 lines (old UI)
- Net: -570 lines

**Implementation Time:**
- Planned: 6-8 hours
- Actual: ~2 hours (clear requirements helped)

**Commits:**
- b8baadd (backend enforcement)
- 988899a (frontend UI)
- 65972da (technical documentation)

## What's Next

### Phase 2: Multi-Player Battles (Future)

**Concept:** 2+ players can gang up on one target

**Features:**
- Multi-select targets in modal
- Corporation team attacks (Corp A vs Corp B)
- Sequential combat resolution
- Loot split among attackers

**Effort:** 8-10 hours

### Phase 3: PvP Zones & War Declarations (Future)

**Concept:** Advanced zone rules + corporation wars

**Features:**
- Zone-specific multipliers (XP/loot bonuses)
- War zones with special rules
- Corporation war declarations
- Alliance mechanics

**Effort:** 10-12 hours

### Phase 1.5: Player Entry Notifications (Soon)

**Concept:** Notify when player enters your sector

**Features:**
- In-game notification on NavScreen
- "⚠️ PlayerName entered sector"
- Only in PvP-enabled sectors
- Optional push notification

**Effort:** 2-3 hours

## Try It Now

**Experience the new PvP system:**

1. Join a galaxy with `pvpEnabled: true`
2. Enter a Pirate or Neutral sector
3. Look for the "⚔️ PvP Zone" badge
4. If players present, tap "⚔️ X players in sector"
5. Select target, initiate combat

**Want safety?** Head to Federation space - always a safe haven.

---

**Technical Details:** See `docs/features/pvp-system.md` for complete implementation guide (15KB, 580 lines).
