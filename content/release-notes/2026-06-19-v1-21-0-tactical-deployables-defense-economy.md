---
title: "v1.21.0 — Tactical Deployables, Defense, and Economy Fixes"
date: 2026-06-19T12:00:00Z
type: blog
description: "v1.21.0 expands tactical deployable control, restores combat-capacity upgrade visibility, rebalances planets and starbases, and fixes several combat, defense, and stale-state issues."
---

v1.21.0 expands tactical options, tightens several combat and defense rules, and removes some stale UI and backend paths that were getting in the way.

This release improves how deployables work in the field, restores clearer upgrade access in port UI, rebalances planet economics, and fixes a cluster of state and defense bugs uncovered after the v1.19.0 and v1.20.0 releases.

## Tactical Deployables and Intel

Limpet Trackers are now more usable as an actual intelligence tool instead of a one-off novelty.

You can plant them directly from the Bridge, deployed limpet count now caps correctly at 10, self-destruction behavior is fixed, and shipyards now support paid limpet detection.

This release also improves field awareness before you commit to movement. Players can now see deployed fighters before warping, deploy multiple mines in one action, and jettison workers intentionally when needed.

## Combat Upgrade Access and Ship UI Cleanup

Stardock once again exposes fighter-capacity and torpedo-capacity upgrades in the UI, restoring access to those progression paths without forcing players to guess where they went.

This build also includes cosmetic cleanup across planet, beacon, and Ship Stats surfaces so the surrounding interface is more consistent while you manage ships and deployments.

## Planet Economy, Defense, and Combat Rules

Planet economy payouts, claim fees, and starbase caps have been rebalanced to better match the current live economy.

On the defense side, Citadels and shields now defend planets correctly even when local garrison counts are low, closing a rules bug that made some developed worlds weaker than intended.

Ghost ships are also fixed and no longer appear present in-sector unless the player's actual active ship is there.

## Backend Cleanup

v1.21.0 removes dead Cloud Function wrappers and retires obsolete notification toggles.

That cleanup does not add a new player-facing feature by itself, but it reduces stale paths in the codebase and lowers the risk of future release-line regressions.
