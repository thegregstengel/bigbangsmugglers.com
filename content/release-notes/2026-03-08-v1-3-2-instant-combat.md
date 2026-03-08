---
title: "v1.3.2 — Instant Combat"
date: 2026-03-08T09:00:00-05:00
description: "v1.3.2 delivers truly instant NPC combat results by computing the fight outcome during your move and writing results in the background."
---

v1.3.2 is a significant architecture improvement to how NPC encounters work.

## What Changed

Previously, when you entered a sector and encountered an NPC, hitting Attack triggered a second backend call that had to cold-start, look up your ship and cargo, resolve the fight, write the results to the database, and then return — all while you waited. This could take anywhere from a few seconds to over a minute.

Now the process is split into two independent steps. When you move into a sector, the server immediately reads your ship stats and computes the fight outcome. That result is sent back with the move response before any database writes happen. When you hit Attack, the recap appears instantly because the outcome is already there.

All the database work — updating your ship damage, marking the NPC defeated, creating loot, updating your stats — happens in the background after your phone already has the answer. You never wait for it.

If you choose to flee, the NPC is despawned and the result is discarded. Your choice to fight or run still matters, but the outcome is computed the moment you arrive.

## Also Fixed in This Release

- Removed the duplicate plain-text combat popup that appeared after battles (v1.2.9)
- Battle recap screen now shows your correct pre-battle stats rather than post-damage values (v1.2.9)
- Fixed stale ship reference after buying a new ship at a starport (v1.2.8)
- Fixed deployable scanning and deployment ship lookup (v1.2.8)
- Fixed turn reset timer showing up to 24 hours instead of the correct 4-hour countdown (v1.2.7)
