---
title: "v1.4.3 — Combat Effects Fixed"
date: 2026-03-10T20:00:00
type: blog
description: "v1.4.3 fixes a critical bug where losing a fight had no consequences — damage, credit loss, and ship disable now all apply correctly."
---

v1.4.3 fixes a critical bug where losing a fight had no real consequences.

## Combat Losses Now Stick

When you lost a fight, the defeat recap screen appeared correctly — but nothing actually changed. Your shields, fighters, and credits were untouched, and your ship was never disabled. The root cause was a Firestore transaction ordering issue: cargo data was being read after several writes had already occurred, causing the transaction to fail silently. The pre-computed recap still displayed, but none of the effects were committed.

This is now fixed. Losing a fight will correctly apply all consequences: shield and fighter loss, credit theft, cargo looting, and ship disable when shields hit zero.
