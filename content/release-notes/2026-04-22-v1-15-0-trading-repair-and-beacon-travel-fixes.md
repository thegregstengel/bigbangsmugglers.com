---
title: "v1.15.0 — Trading, Repair, and Beacon Travel Fixes"
date: 2026-04-22T18:00:00-04:00
type: blog
description: "v1.15.0 improves port trading, Repair Station reliability, navigation stability, and beacon travel quality of life across the live Android release."
---

v1.15.0 improves several of the most common day-to-day actions in Big Bang Smugglers: trading, repairing, navigating, and moving between beacon locations.

This release also clears out a cluster of state-sync issues that were making some screens look wrong even when the underlying game data was correct.

## Better Trading Max Calculations

Port trading Max buttons now respect both available hold capacity and current port stock.

That means the buy flow stops overfilling the quantity field with values your ship cannot actually carry.

## Repair Station Behavior That Matches Ship State

Repair Station checks and repair/refill messaging now line up with the ship's real status.

That covers the cases where shields, fighters, torpedoes, or other repair-state prompts were behaving inconsistently.

## Stability and State Fixes Across Core Screens

v1.15.0 fixes Nav load failures, profile name saves that did not persist, corp-access state falling back incorrectly, planet personnel deployment refresh issues, PvP immunity enforcement, and advanced-upgrade installed-state display after returning to port.

## Beacon Quality-of-Life Improvements

Beacons are now easier to manage and use as travel anchors.

Players can recall or destroy their own beacon, and ships with warp drive can warp directly from beacon cards instead of manually re-entering destination sectors.
