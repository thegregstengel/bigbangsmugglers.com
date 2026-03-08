---
title: "Planet Combat, Intel Brokers & Starport Fixes"
date: 2026-02-21
description: "Planet attack system, intel broker service, defense station PvP immunity, structure building UI, and 4 parallel agent fixes. 14 issues closed."
draft: false
sidebar:
  exclude: true
toc: false
---

Big night. 14 issues closed across two parallel workstreams — new features going in while bugs from yesterday's QA session got fixed simultaneously.

## New Features

**Planet Combat**

You can now attack enemy planets. Raid them for loot, hold them with your garrison, lose them if you leave them exposed. The planet raid system closes the loop on one of the biggest gaps from the [Feb 6th planets audit](/blog/2026-02-06-planets-warp-trade) — we had colonization and production, but no way to actually fight over territory. That changes today.

**Intel Broker**

Research and information ports now have an intel broker service. You can pay for sector intelligence — enemy positions, trade data, strategic info. It's the kind of service that makes the information economy feel real. Smugglers don't just move cargo; they move knowledge.

**Defense Station PvP Immunity Contracts**

Defense stations now offer paid PvP immunity contracts. Pay the station, get a protection window. This creates meaningful decisions — spend credits on safety, or gamble on flying unprotected.

**Planet Structure Building UI**

The backend for planet structures already existed. Today we shipped the frontend — you can now actually build structures on your planets through the UI. The Structures tab on the planet landing screen is live.

## Parallel Bug Fixes (#270-273)

While features were going in, a separate agent pass closed four bugs discovered from QA:

**#270 — Negative upgrade values**
`shipGetInfo` was showing negative `maxUpgrades` for the starter ship. The upgrade formula was treating the base tier as a subtraction point instead of a floor. Fixed.

**#271 — classKey mismatch**
The starter ship document stored `classKey: 'scout'` but the API was returning `'frontier_scout'`. A string mismatch that cascaded through any code doing class lookups. Fixed — standardized to `frontier_scout`.

**#272 — Ship purchase failing at Federation starport**
`shipPurchase` was failing with "No ship purchase facility" even at a Federation starport. The query was using a compound index that didn't work for the starport lookup. Fixed with a direct document lookup instead.

**#273 — Mission payload not unwrapping**
`acceptMission` was throwing "Mission ID is required" because the Cloud Function was reading `data.missionId` when the payload was wrapped one level deeper. Simple unwrap fix — payload structure standardized.

---

14 issues in one session. Planet combat alone was months in the making — it required the garrison system, the colonize functions, the combat resolver, and the planet structure backend to all be in place first. Tonight they connected.

The galaxy just got a lot more dangerous.
