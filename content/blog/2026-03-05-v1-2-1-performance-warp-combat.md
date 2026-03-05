---
title: "v1.2.1 — Performance, Warp, and Combat Fixes"
date: 2026-03-05
description: "Version 1.2.1 dramatically improves app-wide performance, fixes warp drive timeouts, corrects combat power display in NPC encounters, and polishes ship repair."
---

Version 1.2.1 is a performance and bug fix release. The game should feel noticeably faster across the board.

## Performance

Every cloud function call -- moving, trading, scanning, combat, warp, everything -- was force-refreshing the authentication token before executing. Firebase tokens are valid for an hour, so this was an unnecessary server round trip on every single action, adding roughly half a second to a full second of latency each time. That is removed. The whole game is faster now.

## Warp Drive

Warp drive was timing out on longer routes. The pathfinding algorithm was reading Firestore one sector at a time during route calculation, which could add up to hundreds of sequential database reads on a large galaxy. The route is now computed once during the preview step and cached. Executing a warp after previewing is near-instant. The cache is invalidated automatically when you move, so a route that gets interrupted by an NPC or anything else requires a fresh preview before warping.

## NPC Encounters

The combat power shown for your ship in NPC encounter screens was always displaying 50 -- the base floor value -- regardless of your actual fighters, shields, and torpedoes. It now reflects your real ship stats. The odds calculation was wrong for anyone with upgraded ships.

## Ship Repair

The repair button was only available when a ship was fully disabled. It now appears whenever fighters, shields, or torpedoes are below their maximum. The stat labels in the repair card also now correctly show fighters, shields, and torpedoes as percentages rather than mislabeling fighters as hull.

## Other Fixes

- Starport weapons upgrade buttons renamed to Buy Fighter and Buy Torpedo
- Starport repair shows correct percentages for all three combat stats
- Ship class stat tuning applied to new ship purchases (existing ships unchanged)
