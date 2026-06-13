---
title: "v1.18.1 — Cinematic Transitions"
date: 2026-06-13T00:00:00Z
type: blog
description: "v1.18.1 completes the cinematic transition system with 19 purpose-built scenes, and ships three bug fixes for planet renames, card styling, and a Nav-tab header."
---

v1.18.1 finishes what v1.18.0 started: every placeholder in the cut-scene system is now replaced by a purpose-made image.

## Cinematic Transitions — Now Complete

19 custom scenes (1024×1536, navy/teal palette) are wired into every major moment in the game: docking at a starport, landing on a planet, entering any store, warping through a system, falling into a wormhole or black hole, winning or losing a fight, buying a new ship, accepting and completing missions, leveling up, joining a corp, and the season-end screen.

Per-store interiors now use variant art — a federation starport looks different from other ports. Two new scenes also ship in this release: wormhole-unstable and season-start.

**Tap to skip** any scene the moment it appears. **Settings → Cinematic transitions** turns them off entirely.

## Bug Fixes

- **Trading post names update on planet rename.** Renaming a planet previously left its trading post showing the old name. The fix refreshes the post name atomically inside the same rename transaction.
- **Planet card styling aligned.** The My Planets and Corp Planets cards now match the navy card palette used across the rest of the app.
- **Warp Drive header cleaned up.** Removed the stray emoji from the Warp Drive card on the Nav tab.
