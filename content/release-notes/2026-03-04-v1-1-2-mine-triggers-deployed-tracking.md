---
title: "v1.1.2 — Mine Triggers and Deployed Mine Tracking"
date: 2026-03-04T10:00:00
description: "Version 1.1.2 fixes mine triggers so enemy ships actually take damage when entering a mined sector, and adds a deployed mine tracker to the Bridge."
type: blog
---

Two mine system fixes that should have been there from the start.

## Mine Triggers Now Work

Mines were not detonating when an enemy ship entered a mined sector. The trigger logic is now in place. When a player moves into a sector containing enemy mines, each mine has a 60% chance to trigger, dealing 30 to 50 damage. Up to 3 mines can trigger per move. Triggered mines are consumed -- they are gone after they fire.

Your own mines never trigger against you.

## Deployed Mine Tracking in the Bridge

The Bridge deployment modal now shows a list of sectors where you have active mines. Previously there was no way to see where your mines were deployed without guessing. Open the Bridge from the navigation screen and your deployed mine locations appear below the deployment controls.

## Other Fixes

- Fixed `planet.id` undefined error that was causing all trading post actions to fail
