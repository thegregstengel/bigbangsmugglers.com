---
title: "v1.10.2 — Combat Stat Fix"
date: 2026-04-02T08:00:35-04:00
type: blog
description: "v1.10.2 fixes a combat bug where ship stat advantages — shields, power, and firepower — were not correctly influencing battle outcomes, resulting in disproportionate losses."
---

v1.10.2 is a targeted combat fix.

This update corrects a bug where significant stat advantages were not carrying their expected weight in battle. Ships with heavy shields or large combat power leads were still suffering total defeats against much weaker opponents — an outcome that should have been rare but was happening too often.

## Combat Outcomes Now Reflect Stat Gaps

The core issue: shields were providing little to no actual damage mitigation, and attrition losses were not scaling with the actual gap between combatants.

In the most clear-cut cases — a ship with 225 shields against one with 39, or a 2:1 combat power advantage — the stronger ship was still taking full losses on defeat. That's now corrected.

With this fix:

- Shields reduce incoming damage proportionally to the actual shield gap between ships
- Defeat losses scale with how close the fight actually was — a dominant stat lead means smaller losses on an unlucky loss, not total annihilation
- A large combat power advantage no longer produces consistent total defeats against much weaker opponents

## Overall

v1.10.2 makes combat outcomes feel fair. If you invest in shields and ship power, that investment should show up in how you absorb a bad result. This fix closes the gap between what the stat screen implies and what actually happens in battle.
