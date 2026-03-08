---
title: "v1.3.2 — Instant Combat"
date: 2026-03-08T01:00:00
description: "v1.3.2 delivers truly instant NPC combat results by computing the fight outcome during your move and writing results in the background."
type: blog
---

v1.3.2 is a significant architecture improvement to how NPC encounters work.

## Instant Combat Results

Previously, when you entered a sector and encountered an NPC, hitting Attack triggered a second backend call that had to cold-start, look up your ship and cargo, resolve the fight, write the results to the database, and then return — all while you waited. This could take anywhere from a few seconds to over a minute.

Now the process is split into two independent steps. When you move into a sector, the server immediately reads your ship stats and computes the fight outcome. That result is sent back with the move response before any database writes happen. When you hit Attack, the recap appears instantly because the outcome is already there.

All the database work — updating your ship damage, marking the NPC defeated, creating loot, updating your stats — happens in the background after your phone already has the answer. You never wait for it.

If you choose to flee, the NPC is despawned and the result is discarded. Your choice to fight or run still matters, but the outcome is computed the moment you arrive.

## Duplicate Combat Popup Removed

After winning a fight, two separate result screens were appearing: an old plain-text popup that fired immediately, and the newer battle recap screen that showed up minutes later. The plain-text popup has been removed. The battle recap screen is now the only result you will see.

The plain-text popup will still appear for one case: incoming PvP attacks where you are the defender. That alert is still useful when you are not actively watching the screen.

## Correct Pre-Battle Stats

The battle recap screen was showing your stats after taking damage rather than your stats going into the fight. The YOU column now shows your fighters, shields, and torpedoes as they were at the start of combat, so you can see what you brought versus what you lost.

## Also Fixed

- Fixed stale ship reference after buying a new ship at a starport (v1.2.8)
- Fixed deployable scanning and deployment ship lookup (v1.2.8)
- Fixed turn reset timer showing up to 24 hours instead of the correct 4-hour countdown (v1.2.7)
