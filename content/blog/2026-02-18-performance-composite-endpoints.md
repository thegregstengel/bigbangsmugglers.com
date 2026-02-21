---
title: "3x Faster Load Times — The Composite Endpoint Overhaul"
date: 2026-02-18
description: "How we cut screen load times by 3x by rethinking how the game talks to the backend"
author: "Dev Team"
---

## The Problem We Didn't Notice (Until We Did)

Every time you opened the Nav screen, the app was making **four separate round trips** to the server:

1. Fetch your player profile
2. Fetch your current sector data
3. Fetch players in your sector
4. Fetch your recent sectors

Each of those four calls also independently read your player document from the database — so your profile was being read **four times** just to load one screen. Multiply that across every tab you visit, and you're looking at a lot of wasted work.

The Ship screen was even worse: **five separate calls**, each reading your player profile independently.

The result was load times between 1000–1500ms just to see your ship stats or navigate a sector. Not great.

## The Fix: Composite Screen Endpoints

The solution was to create a dedicated "screen data" endpoint for each major screen. Instead of firing multiple calls, the app makes **one call**, the server does all the reads in parallel internally, and everything comes back at once.

```
Before:
  playerGetProfile()        → 400ms
  navGetCurrentSector()     → 400ms  
  getPlayersInSector()      → 400ms  ← also read players/{uid}
  navGetExploredSectors()   → 400ms  ← also read players/{uid}
  Total: ~1500ms

After:
  navGetScreenData()
    ├── ship query     ─┐
    ├── galaxy doc     ─┤ all parallel
    └── recent sectors ─┘
    then: sector + POIs + players in sector (parallel)
  Total: ~500ms
```

**Same data. One third of the time.**

## What Changed Screen by Screen

### 🗺️ Nav Screen
**Before:** 4+ calls, your profile read 4 times, client-side Firestore query for PvP settings  
**After:** 1 call, 3-wave parallel execution

The players-in-sector query got a major overhaul too. Previously it loaded every player in the galaxy and checked each one's ship to see if they were nearby — an O(n) operation that gets slower as galaxies fill up. Now it queries ships directly by sector ID. Fast and index-backed regardless of galaxy size.

### 🚀 Ship Screen
**Before:** 5 calls on mount — profile, ship info, faction info, missions, recent sectors  
**After:** 1 call. Faction info is now computed inline (it's pure math on your profile data — no extra database reads needed at all).

### 🍀 Feed Screen  
**Before:** Sequential load chain — profile had to load before feed could load, missions couldn't start until both were done  
**After:** 1 call returns everything. Also fixed a silent bug where the feed was being fetched twice on every screen open (two `useEffect` hooks both triggering the same load).

### 🏆 Leaderboards
**Before:** Profile + season info + leaderboard — 3 separate calls, season countdown never worked  
**After:** 1 call. Bonus fix: the season name and countdown timer were broken because the response shape was nested one level too deep. Now they work correctly.

### 🏛️ Starport Screen
**Before:** Player and starport reads happened sequentially (needed player first to validate galaxy), ship info loaded again on modal open  
**After:** All three reads fire in parallel. Ship info is pre-loaded on mount, so the Shipyard and Ship Sales modals open **instantly** — no spinner.

## The Architecture

All five composite endpoints follow the same pattern documented in `docs/architecture/composite-screen-data.md`:

- **One player document read** per screen load (was 3–5x)
- **`Promise.all()`** for all independent reads
- **Graceful degradation** — each parallel read has its own error handler, so a failed recommendation fetch can't crash your feed
- **Minimal payloads** — each endpoint returns exactly what the screen needs, nothing extra

## Naming Convention

Going forward, screen data endpoints follow a clean naming convention — no version suffixes:

- `feedGetScreenData`
- `leaderboardGetScreenData`
- `shipGetScreenData`
- `navGetScreenData`
- `starportGetScreenData`

## Other Fixes in This Update

- **Feed real-time listener fixed** — the live feed update listener was failing with a permissions error. Firestore security rules can't evaluate document field values on collection queries, so the rule was rejecting the listener before returning any results. Fixed with a query-compatible rule.

- **Negative bank balance bug** — found and fixed a race condition where the repair and deployables functions could push your bank balance below zero. Two transactions could both read "you have 5,000 credits," both think they can deduct 3,700, and both do — leaving you at -1,400. Added double-check validation inside the transaction before any deduction.

- **Trading logic** — confirmed that trading (buy/sell) has always correctly used wallet credits first, never touching the bank unless you explicitly deposit or withdraw. The bank balance bug was isolated to the repair and deployables systems.

## Scorecard

| Screen | Calls Before | Calls After | Improvement |
|--------|-------------|-------------|-------------|
| Feed | 3 | 1 | ~3x |
| Leaderboards | 3 | 1 | ~3x |
| Ship | 5 | 1 | ~5x |
| Nav | 4+ | 1 | ~3x+ |
| Starport | 2 (sequential) | 1 (parallel) | ~2x |

Every major screen in the game now loads with a single round trip to the server. The database reads the same data — it just does it smarter.

---

*These improvements are live now. No app update required.*
