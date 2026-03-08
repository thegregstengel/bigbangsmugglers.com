---
title: "Multiplayer Systems Audit"
date: 2026-02-06
description: "Part 2 of the Feb 6 sprint: PvP disabled, leaderboards hardcoded, no chat, no corps — the full multiplayer gap report."
draft: false
sidebar:
  exclude: true
toc: false
---

This is part 2 of the February 6th audit. While one track covered missions and performance, we ran a parallel deep dive into everything multiplayer: PvP, leaderboards, NPCs, and social systems.

The headline: a lot of it was scaffolding.

## PvP: Disabled and Orphaned

The PvP combat system had been disabled — the Cloud Functions removed — but the UI was still there. Players could see combat controls. Nothing behind them worked. Combat notifications? Missing. Attacked players weren't notified. The player detection system existed but its only consumer was the disabled combat code.

There was also orphaned library code — `CombatResolver` and `ShipRoles` — sitting in the codebase with no active callers. Good logic, going nowhere.

## Leaderboards: Hardcoded Everything

The leaderboard UI was showing hardcoded placeholder data. Not stubbed-with-a-TODO hardcoded — actually hardcoded names and numbers that looked real. The Cloud Function that should serve leaderboard data didn't exist, so the frontend had been doing it all client-side.

Beyond that: no XP-based category, no exploration leaderboard, no faction leaderboard. Season info wasn't connected to real data. Named ranks (Recruit, Captain, etc.) didn't display. Real-time updates during active seasons weren't implemented. Corporation leaderboards were missing entirely. Anti-boosting measures: not implemented.

## NPCs: Dead Config, Dead Code

The NPC system had configuration that was never applied (`npcEncounterRate` sitting in config, going unused), UI controls that referenced NPC actions but did nothing, and the core `CombatResolver` NPC logic path that never actually triggered.

We filed a full NPC roadmap: type system (Pirates, Traders, Patrols), Firestore schema, spawn system wired into `navMove`, loot drop system, encounter UI and modals, documentation.

## Social: Doesn't Exist

No chat. No messaging. No alliances. No player-to-player trading (that's a trade-system issue too, but it's fundamentally social). No faction victory conditions. No cosmetic award system. Corporation advanced features (missions, notices, war declarations) — incomplete.

This wasn't a surprise. We knew social systems were future-roadmap. But documenting the exact gaps lets us plan the build order properly.

## What Shipped From This

Several of these issues got immediately resolved — leaderboards got a proper Cloud Function, named ranks shipped, the XP category was added, season info got wired up. The NPC system got its foundation laid. The rest became the multiplayer backlog.

Knowing what you don't have is the first step to building it.
