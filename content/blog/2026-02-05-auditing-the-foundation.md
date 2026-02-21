---
title: "Auditing the Foundation"
date: 2026-02-05
description: "23 issues filed across UI wiring gaps, dead buttons, and broken API chains — setting the stage for the build sprint."
draft: false
sidebar:
  exclude: true
toc: false
---

Before you can build fast, you have to know what's actually broken.

We spent February 5th doing a full audit of the codebase — UI wiring, function exports, duplication — and we weren't gentle. By the end of the day we had filed 23 GitHub issues across three categories: UI wiring gaps, function audit failures, and duplication problems.

## What We Found

**UI Wiring Gaps**

Dead buttons everywhere. `ShipServicesSubScreen` was calling `shipRename` without a `shipId`. `shipUpgrade` had a parameter mismatch. The MapScreen's Deploy Defenses button was a stub. Combat and repair buttons on `CombatScreen` — stubs. Stations screen — stubs. `PlanetsScreen` was rendering hardcoded data instead of hitting the backend at all.

These weren't edge cases. These were the main flows.

**Function Audit Failures**

We ran a full audit of the Cloud Functions layer. What we found:

- `auth/bootstrap.ts` was written in v2 syntax but never exported — the auth bootstrap literally didn't exist
- Ship restock functions were exported as callables when they're supposed to be scheduled triggers
- `updateMissionProgress` — a callable function that no UI code ever calls
- Season automation functions exported but never invoked
- Shipyard management functions with no frontend service wired up
- `adminCreateEnhancedSeason` deprecated but still actively exported
- Economy functions entirely commented out due to compilation errors
- Auto-destruction functions same deal — commented, broken

**Duplication**

Ship rename appeared in two screens. Ship upgrades in two screens. Mission board in two screens. We flagged those for consolidation — they'd been copied instead of abstracted.

## Why We Did This

We were about to start a major build sprint. You don't want to discover that a function doesn't exist when you're three features deep and blocked. Better to know now.

The 23 issues became our sprint backlog. Every "coming soon" on the starport redesign post? This audit is why those dates were real commitments, not vague promises.

The house needed an inspection. We did the inspection.
