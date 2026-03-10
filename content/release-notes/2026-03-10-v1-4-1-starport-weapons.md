---
title: "v1.4.1 — Starport Weapon Purchase"
date: 2026-03-10T13:00:00
type: blog
description: "v1.4.1 wires up bulk fighter/torpedo purchase in the TriStar Shipyard and fixes combat loot not triggering when a player had zero credits."
---

v1.4.1 finishes the weapon purchase system introduced in v1.4.0 and fixes a loot calculation bug.

## Weapon Purchase in TriStar Shipyard

The Fighter Bay and Torpedo Bay are now available inside the TriStar Shipyard & Maintenance Bay at any starport. Use the quantity stepper to buy as many fighters or torpedoes as you want at flat prices — 75 credits per fighter, 150 credits per torpedo — up to your ship's maximum capacity.

## Combat Loot Fix

When a player had zero credits, the loot calculation was treating that as a falsy value and skipping all cargo loot as well. A player with empty pockets but a full cargo hold could be attacked and lose nothing. This is fixed — credits and cargo are now evaluated independently, and stolen cargo amounts are clamped to what the player actually has.
