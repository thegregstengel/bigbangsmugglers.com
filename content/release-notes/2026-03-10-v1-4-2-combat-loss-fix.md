---
title: "v1.4.2 — Combat Loss Effects Fixed"
date: 2026-03-10T16:00:00
type: blog
description: "v1.4.2 fixes combat losses having no real consequences — ship damage, credit loss, and cargo theft now all apply correctly."
---

v1.4.2 fixes several bugs where losing a fight had no real consequences.

## Combat Loss Effects Now Apply

When you lose a fight against a non-aggressive NPC, the battle results are now fully committed before the recap screen appears. Previously the commit was fire-and-forget — if it failed silently, you'd see the defeat recap but nothing would actually change. Now the app waits for the commit, shows a spinner during the brief wait, and only shows the recap once effects are locked in.

## Credits Now Looted on Loss

When an NPC wins, it was correctly stealing your cargo but never deducting your credits. That's fixed — credits are now taken along with cargo when you lose.

## Auto-Repair Grace Period

Ships that were just disabled in combat are now protected from the auto-repair system for 60 seconds. This prevents a race condition where a ship could be disabled by combat and immediately restored on the same turn reset, making the defeat feel consequence-free.
