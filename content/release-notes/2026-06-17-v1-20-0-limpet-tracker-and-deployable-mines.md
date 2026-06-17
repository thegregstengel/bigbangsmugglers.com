---
title: "v1.20.0 — Limpet Tracker and Deployable Mines"
date: 2026-06-17T00:00:00Z
type: blog
description: "v1.20.0 introduces the Limpet Tracker, a new deployable that plants in a sector and latches onto passing ships for real-time location tracking. Proximity mines now trigger on warp entry. The Hangar moves to Starport and Starbase with improved ship valuation and a sell payout increase to 64%. Critical fixes for bounty collection, Starbase construction, planet fighter deployment, and pirate port alignment."
---

v1.20.0 sharpens the deployable layer and ships a batch of critical fixes from v1.19.0.

The headline is the Limpet Tracker — the first device in the game designed for intelligence gathering rather than direct combat. Proximity mine behavior also closes a long-standing warp loophole, and the Hangar gets a proper home as a visitable location with better trade-in terms.

## Limpet Tracker

The Limpet Tracker is a new deployable available for purchase at ports.

Plant one in a sector and it waits. When a ship warps through, the limpet latches on and begins reporting that ship's location in real time until it's swept. Captains can inspect their own hull at any time to find and remove attached limpets.

The Ship screen also now lists all mines you have deployed across sectors, giving you a full picture of your placed devices without leaving the interface.

Mine owners receive a feed entry and a push notification whenever one of their proximity mines detonates — wherever it happens.

## Proximity Mines Now Trigger on Warp

Until this release, warping into a mined sector bypassed mine triggers entirely. Ships could pass through without detonating anything.

That gap is closed. Mines now detonate on any entry vector — warp or conventional navigation.

## Hangar Improvements

The Hangar has moved out of the Ship tab and is now a visitable location accessible from Starports and Starbases, consistent with how other ship services are accessed.

Each ship listing now displays both its original purchase price and current estimated value side by side. The sell payout has also increased from 50% to 64% of current value.

## Bug Fixes

Four significant bugs are resolved in this release.

**Bounty collection** — the "not at a starport" error when collecting a bounty from a starport is fixed. The function was checking a stale sector field on the player document instead of the active ship's sector.

**Starbase construction** — building a Starbase no longer takes your credits without delivering the structure. State was failing to persist after payment in some cases.

**Planet fighters** — deploying fighters from a planet now correctly adds them to your deployed-units list. Previously they reduced the planet's fighter count without appearing anywhere trackable.

**Pirate port alignment** — attacking a pirate port now shifts your alignment toward the Federation as intended. The effect was previously reversed.
