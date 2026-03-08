---
title: "v1.1.1 — Planet Production and Stability Fixes"
date: 2026-03-03T10:00:00
description: "Version 1.1.1 fixes the planet production system, aligns production ticks to 4-hour boundaries, and adds region multipliers to actual output."
type: blog
---

A focused patch on planet production, which had several bugs that prevented planets from producing reliably.

## Planet Production Fixes

The production tick query had a Firestore index issue that caused it to silently return zero planets, meaning nothing was actually producing. That is fixed. The collect function also had a bug where it failed to reset the production ready flag after collection, which caused the scheduling gate to break on subsequent ticks.

Production ticks are now aligned to the same 4-hour UTC boundaries used by turn resets and ship repair (00:00, 04:00, 08:00, 12:00, 16:00, 20:00 UTC). The region multiplier -- which adjusts output based on where in the galaxy the planet sits -- is now applied at tick time rather than only at display time, so actual output matches what the UI shows.

Base output per tick is approximately 14 fuel, 10 organics, and 5 equipment, scaling with region and structures.

## Other Fixes

- Fixed callable wrapper pattern on trading post and bounty functions that was causing intermittent failures
- Settings screen now correctly shows the current app version instead of a hardcoded value
- Stale refresh button removed from the no-galaxy state on the navigation screen
