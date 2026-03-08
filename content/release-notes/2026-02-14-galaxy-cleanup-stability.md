---
title: "Galaxy Cleanup & Stability"
date: 2026-02-14
description: "Galaxy destruction now cleans up starports and all related collections; player stats reset properly on season exit."
draft: false
sidebar:
  exclude: true
toc: false
---

When a galaxy ends, it should actually end.

We found two issues with our galaxy destruction process that meant old data was lingering after a season closed. We fixed both, plus cleaned up a player stats issue that was carrying state between seasons.

## Starports Weren't Being Cleaned Up

When a galaxy was destroyed, the starport documents were orphaned. The galaxy was gone but the starport collection was still sitting in Firestore. That's unnecessary storage, and it's the kind of ghost data that causes confusing edge cases if a galaxy ID ever gets reused.

We updated the galaxy destruction process to include starports in the cleanup pass.

## Multiple Collections Left Behind

Same problem, broader scope. Beyond starports, several other subcollections weren't being wiped on galaxy destruction. We audited the full set of collections created during galaxy initialization and made sure the cleanup function mirrors it — everything created on start gets destroyed on end.

Clean slate means clean slate.

## Player Stats Not Resetting on Season Exit

When a player left a galaxy (voluntarily or via season end), their in-season stats were persisting. Join a new galaxy and you'd carry forward stale progression data from the last one.

This was filed alongside the mission persistence bug from Feb 12th — same root cause, different collection. Stats, missions, any season-scoped data now gets cleared when a player exits.

---

None of these were user-facing features. None of them had a UI. But they're exactly the kind of infrastructure correctness that makes the rest of the game trustworthy. When a season ends, it ends. When you join a new galaxy, you start fresh.

That's how it should work. Now it does.
