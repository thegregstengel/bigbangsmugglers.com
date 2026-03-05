---
title: "v1.2 — Ship Upgrades, Performance, and Combat Fixes"
date: 2026-03-04
description: "Version 1.2 overhauls ship upgrade limits, sharpens class identities, dramatically improves app performance, and fixes a pile of bugs."
---

Version 1.2 focuses on making the game feel faster, clearer, and more fair.

## Ship Class Overhaul

Ship classes now have genuinely distinct identities. Previously, all classes shared the same shield values and the stat differences between a trading ship and a warship were easy to miss. That changes in 1.2.

**Trading ships** (Nebula Merchant line and Smuggling equivalents) now carry significantly more cargo and have a 55% escape rating. They are not built for fights -- their edge is in hauling and running.

**War ships** (Patrol Corvette line and Raider equivalents) are glass cannons. They have dramatically higher fighter and torpedo counts but very low escape (25%) and minimal cargo. If you fly one, you commit to the fight.

**Balanced ships** (Frontier Scout line and Corsair equivalents) now have substantially more shields, making them the most durable option. They sit between trading and war ships on firepower and cargo.

## Fighter and Torpedo Upgrade Limits Doubled

Upgrade caps for fighters and torpedoes have been doubled across all ship classes. A ship that previously capped at 30 fighters can now reach 40. The caps still scale by class -- war ships benefit most.

## Upgrade Costs Visible Before You Click

The starport now shows the cost of each upgrade on the button itself before you commit. No more guessing what the next hold or fighter upgrade will run you.

## Ship Store Shows Start and Max Stats

When browsing ships to buy, every stat now shows the starting value and the upgrade ceiling. You can compare not just what a ship starts with but how far it can go.

## Performance

Every cloud function call in the app was unnecessarily refreshing the authentication token on each request. This added roughly half a second to a full second of latency to every single action -- moving, trading, scanning, combat, everything. That is gone now.

Warp drive was timing out on long routes because pathfinding read Firestore one sector at a time during the route calculation. The route is now computed during preview and cached, so executing a warp after previewing it is near-instant.

## Bug Fixes

- NPC encounter screen now shows your actual combat power instead of always showing the base value of 50
- Ship repair is now available whenever fighters, shields, or torps are below max, not only when the ship is fully disabled
- The ship screen no longer goes blank after buying fighters or torpedoes
- Torpedoes now correctly restore during auto-repair at turn reset (the field name was wrong)
- Planet descriptions now appear on the planet landing screen
- Claiming a planet now correctly marks it as claimed for all players
- Trading post actions no longer fail with a missing planet ID error
- Combat power breakdown on the ship screen now labels the base floor clearly
