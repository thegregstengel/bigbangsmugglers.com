---
title: "v1.5.1 — Bridge Tab Polish"
date: 2026-03-13T14:00:00
type: blog
description: "v1.5.1 cleans up the Bridge tab on the Ship screen — consistent card styles, separate beacon and mine cards, better layout."
---

v1.5.1 is a polish pass on the Bridge tab and a fix for warp drive route calculation hanging on long distances.

## Warp Drive Route Fix

Calculating a warp route was timing out for long distances. The pathfinding was making a separate database read for every sector it explored — in a large galaxy that's hundreds of sequential round trips, easily pushing past the timeout limit. The fix loads all sector connections in a single batch query and runs the pathfinding entirely in memory. Warp route previews and navigation should now be instant regardless of distance.

## Bridge Tab Cleanup

The redundant "Bridge" heading and subtitle have been removed — the tab label is enough. The Warp Drive section is now wrapped in a proper card matching the style of the scan and recon cards below it.

The deploy section has been split into two separate cards: one for Navigation Beacons and one for Proximity Mines. Each card shows your current inventory count and a deploy button, with a hint to buy more at the starport when you're out.

Card order is now: Warp Drive, Beacons, Mines, Scan, Recon, Scan Deployables — grouped logically with consistent styling throughout.
