---
title: "Quality of Life Fixes"
date: 2026-02-12
description: "Four polish fixes: XP display, nav screen refresh after warp, mission persistence across seasons, and a screen notch overflow."
draft: false
sidebar:
  exclude: true
toc: false
---

Not every update is a major feature. Sometimes you just fix the things that quietly annoy players every session.

February 12th was one of those days — four fixes, all polish, all feel.

## XP Display Was Lying

The warp drive purchase screen was showing "0/100 XP" for a player who had 1,227 XP. That's a bad look. The field read was wrong — it was pulling from the wrong path in the player doc. Fixed. Now the XP requirement actually reflects your real progress.

## Nav Screen Stuck on "DISABLED" After Repair

After repairing a disabled ship, the Nav screen was still showing "Status: DISABLED." The screen wasn't refreshing. The fix was straightforward — we added a `navRefreshKey` to `GalaxyContext` and trigger it after warp and repair events. The screen now updates properly when your ship status changes.

## Missions Persisting Across Galaxies

If you had an active mission when a galaxy ended, that mission would still be there when you joined a new season. Wrong galaxy, wrong mission board — but the mission was hanging around in your data. We fixed the season cleanup to properly clear accepted missions when a player leaves or a galaxy is destroyed.

## Season Browser Notch Overflow

The season browser screen was overflowing into the device notch on some phones. A layout constraint issue — content wasn't respecting the safe area. Clamped and fixed.

---

None of these were crashes. None were blockers. But they're exactly the kind of friction that makes a game feel unpolished. Players notice these things. We noticed them too.

Shipped.
