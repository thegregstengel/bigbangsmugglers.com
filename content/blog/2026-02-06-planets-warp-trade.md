---
title: "Planets, Warp & Trade"
date: 2026-02-06
description: "Part 3 of the Feb 6 sprint: planet feature gaps catalogued, warp drive system designed and queued, trade system improvements scoped."
draft: false
sidebar:
  exclude: true
toc: false
---

The third track from February 6th covered the planet system, warp drive, and trade. A lot of backend was there — UI wasn't keeping up.

## Planets: Backend Ahead of Frontend

The planet system had real depth on the backend. Functions for deposits, withdrawals, daily production ticks, collection — all implemented, all undocumented or mis-documented.

What we found in the audit:

- The planet-system built doc claimed 100% complete. It was not.
- `FUNCTIONS_INDEX.md` was missing 5 planet functions entirely
- `PlanetsScreen.md` wasn't in `SCREENS_INDEX.md`
- Documentation for `planetDailyProductionTick`, `planetProductionCollect`, `planetWithdraw`, and `planetDeposit` were all missing
- The production ready flag existed in backend data but wasn't surfaced in the UI
- No garrison management function implemented
- No planet transfer or ownership change function
- No population growth over time
- No planet defense or raid combat system

The backend team had done solid work. Docs and UI just hadn't caught up. We filed the tickets, corrected the specs, and built the planet roadmap from scratch.

## Warp Drive: Designed, Scoped, Queued

Warp drive was scoped out fully on Feb 6: six features from foundation through UI.

The plan:
1. Sector visit tracking subcollection (foundation for BFS pathfinding)
2. Warp navigation Cloud Function with BFS shortest-path
3. Warp drive install and upgrade Cloud Functions
4. Install/upgrade UI at port ship services
5. Beacon system for marking and quick-warping sectors
6. Explored tab on ShipScreen with sector history and warp UI

All six became GitHub issues. All six shipped.

The warp drive UX we eventually shipped — type a sector, preview the route, then commit — came directly from the design work on this day.

## Trade: Gaps and Goals

Trade system audit was shorter. The contraband detection system was incomplete on the backend. Cargo lot selection in the UI only showed the first matching lot — if you had two lots of the same commodity, you couldn't pick which one to sell. Player-to-player trading was missing (flagged as both a trade and social gap).

We also documented `TradingSubScreen` properly for the first time — it had no spec at all.

---

Three posts, one day. The Feb 6 audit session was the most productive single day of documentation work we've done. By end of day we had a clear, prioritized picture of what needed to ship — and we started shipping it.
