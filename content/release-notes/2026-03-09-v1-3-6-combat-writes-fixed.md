---
title: "v1.3.6 — Combat Rewards Fixed"
date: 2026-03-09T12:00:00
type: blog
description: "v1.3.6 fixes NPC combat writes not applying — loot, damage, and ship disable were all silently broken."
---

v1.3.6 fixes a significant bug where NPC combat had no real consequences.

## What Was Broken

After the instant combat changes in v1.3.1–v1.3.4, none of the combat results were actually being saved. Win or lose, your ship took no damage, you received no loot, and disabled ships stayed active. The battle recap showed the correct outcome — but nothing behind it was real.

Two separate bugs combined to cause this:

**Background execution:** Cloud Functions v2 does not reliably run code after a response is sent. The previous architecture used a "fire and forget" pattern to apply combat effects after returning the move result to the app. In practice, this meant the writes were silently dropped.

**Wrong field name:** Ship documents store torpedo count as `torps`, but the combat engine was reading `torpedoes` — which doesn't exist on the document. Every ship had an effective torpedo count of zero in every fight.

## What's Fixed

Combat effects are now applied before the response is returned, not after. All three NPC combat paths — ambush encounters, confirmed attacks on non-aggressive NPCs, and player-initiated attacks — now route through a single unified writer that handles ship damage, loot, NPC status, feed messages, and mission progress. The torpedo field name mismatch is also corrected.

Combat outcomes are now real.
