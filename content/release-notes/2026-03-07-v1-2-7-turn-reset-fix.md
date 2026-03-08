---
title: "v1.2.7 — Turn Reset Fix"
date: 2026-03-07T14:00:00
description: "Version 1.2.7 fixes the turn reset timer bug where countdowns could show up to 24 hours instead of the correct 4-hour cycle."
type: blog
---

Version 1.2.7 is a focused bug fix for the turn reset timer.

## What Was Wrong

After your turns reset, the countdown timer could display wildly wrong values — sometimes showing nearly 24 hours remaining instead of the expected 4 hours or less. This happened because the backend had two separate turn reset systems that used different logic. The main movement system used the correct 4-hour UTC boundaries, but the profile system still used an older midnight-only reset check. Whichever one ran last would overwrite the stored timer value, and if the midnight-based path fired, it would write a reset time roughly 24 hours in the future.

## What Changed

All turn timer calculations across the backend now use a single shared utility. Whether you are moving between sectors, scanning, viewing your profile, or joining a galaxy, the math comes from one place and always snaps to the same 4-hour UTC boundaries: midnight, 4 AM, 8 AM, noon, 4 PM, and 8 PM. The fix also covers trading post refill cooldowns, planet production ticks, and robbery cooldowns, all of which shared the same boundary logic.

The new utility ships with a full test suite covering boundary transitions, edge cases, and the "stale stored value" scenario that caused the original bug.

## What to Expect

Turn timers should now show accurate countdowns. If you still see a long timer after updating, run a move or open your profile to trigger a recalculation against the corrected system.
