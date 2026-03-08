---
title: "Bug Fix Sprint"
date: 2026-02-08
description: "8 quick bug fixes after the audit — credits in the wrong field, crashes, and a misnamed leaderboard tab."
draft: false
sidebar:
  exclude: true
toc: false
---

After the audit blitz on Feb 5-6, we had a clear list of what to fix first. February 8th was pure execution — 8 bugs closed, fast.

## The Fixes

**Credits in the wrong field (twice)**

Two separate functions were reading `bank.credits` instead of the player's wallet. The warp drive purchase showed 0 XP because it was reading `playerData.xp` instead of `stats.xp`. The repair function had the same pattern — reading a stale or wrong field. Both shipped same day.

**Repair button not on Ship screen when disabled**

When your ship was disabled, you couldn't repair it from the Ship screen. The repair button wasn't wired there. We added it. Now when you're disabled, you don't have to hunt around for where to fix things.

**NPC combat crash**

`undefined` value in a Firestore document was crashing the NPC combat resolver. A bad write somewhere upstream was leaving a field unset; the combat code didn't guard against it. Fixed.

**Production tab crash**

The planet Production tab was crashing because `nextProductionDate` was undefined. Simple null guard — no more crash.

**Leaderboard tab label**

The leaderboard tab said "Leaderboard." It should say "Leaderboards" (plural — there are multiple categories). Tiny fix, but it bothered us every time we saw it.

**Transaction credits bug (critical)**

This one was important: all transactions were incorrectly using `bank.credits` instead of the wallet. That meant purchases were checking the wrong balance. A player could have 10,000 cr in their wallet and be rejected on a 500 cr purchase because their bank was at zero.

**Leaderboard wealth calculation**

Related to the credits issue — leaderboard wealth was only counting wallet credits, missing bank deposits. A player who banked aggressively looked artificially poor on the leaderboard.

**Mission notification crash**

`forEach` crash in `missionNotifications` when selling at a port. The array it was iterating over could be undefined if no missions were active. Added a guard.

---

Eight bugs. One day. The audit gave us the map — the fix sprint got us moving.
