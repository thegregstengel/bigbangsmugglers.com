---
title: "v1.3.0 — Instant Combat"
date: 2026-03-07T22:00:00
description: "Version 1.3.0 rearchitects NPC combat to resolve instantly when you hit Attack, with no second network round-trip."
---

Version 1.3.0 is a significant architecture improvement to how NPC encounters work.

## What Changed

Previously, when you entered a sector and encountered an NPC, hitting Attack triggered a second backend call that had to cold-start, look up your ship and cargo, resolve the fight, write the results, and then return — all while you waited. This could take anywhere from a few seconds to over a minute.

Now, when the server rolls an NPC encounter as you move into a sector, it resolves the combat immediately as part of that same move. The full result — who won, what was lost, what was looted — is ready before the encounter modal even opens. When you hit Attack, the recap appears instantly because the work is already done.

If you choose to flee, the NPC is despawned and the result is discarded. Your choice to fight or run still matters, but the outcome is computed the moment you arrive.

## Auto-Aggressive NPCs

NPCs that attack on sight (pirates in deep pirate space, for example) still trigger through the original path since the player has no choice to flee. This will be unified in a future update.

## Other Improvements

- Turn consumption for NPC combat is now handled as part of the move, so your turn count updates immediately with the move response rather than after a separate call.
- Mission progress for NPC defeats is tracked correctly in the same flow.
