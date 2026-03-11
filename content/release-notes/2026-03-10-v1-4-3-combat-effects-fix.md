---
title: "v1.4.3 — Combat Loss Fixes"
date: 2026-03-10T20:00:00
type: blog
description: "v1.4.3 fixes several bugs where losing a fight had no real consequences — damage, credit loss, cargo theft, and ship disable now all apply correctly."
---

v1.4.3 fixes a series of bugs where losing a fight had no real consequences.

## Combat Losses Now Stick

When you lost a fight, the defeat recap screen appeared correctly but nothing actually changed. Your shields, fighters, and credits were untouched, and your ship was never disabled. This happened in two different ways:

For non-aggressive NPCs, the combat commit was fire-and-forget — if it failed silently, you'd see the recap but no effects applied. The fix: the app now waits for the commit before showing the recap, and surfaces an error if something goes wrong.

For all NPC encounters, a Firestore transaction ordering issue caused the commit to fail silently — cargo data was being read after several writes had already occurred. The fix restructures the transaction so all reads happen before any writes.

## Credits Now Looted on Loss

When an NPC won, it was correctly stealing your cargo but never deducting your credits. Credits are now taken along with cargo when you lose.

## Auto-Repair Grace Period

Ships disabled in combat are now protected from the auto-repair system for 60 seconds. This prevents a race condition where a ship could be disabled and immediately restored on the same turn reset, making the defeat feel consequence-free.
