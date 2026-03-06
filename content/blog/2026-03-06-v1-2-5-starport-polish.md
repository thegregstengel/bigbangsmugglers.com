---
title: "v1.2.5 — Starport Polish & Ship Stats"
date: 2026-03-06T14:00:00
description: "Version 1.2.5 fixes cargo hold display, ship upgrade resets, the repair button showing on healthy ships, and turn reset clock accuracy."
---

Version 1.2.5 is a polish pass on the starport and ship screen, fixing a cluster of display and behavior bugs reported by players.

## Ship Stats Display

The ship screen stat cards now show consistent information across all four stats. Holds displays your current hold count with the maximum you can reach through upgrades underneath, matching the format used by fighters and torpedoes. The previous display was showing cargo used versus cargo capacity, which belongs in the cargo hold section below.

Fighters and torpedoes now correctly show the repair maximum — base stats plus purchased upgrades — instead of the upgrade ceiling. The upgrade ceiling (how high you can go with future purchases) was inflating the max value and making ships look more damaged than they were.

## Starport Repair

The repair button no longer appears when your ship is in full health. Previously, ships with zero base fighters or torpedoes (scouts, freighters, and most trading vessels) always showed the repair button because the fallback maximum was hardcoded to 100, making zero fighters look like damage. The repair section now only appears when there is actually something to repair.

## Cargo Hold Upgrades

Upgrading cargo holds no longer resets your hold count to a wrong value. The upgrade system was recalculating all ship stats from the ship class definition after every purchase. If the backend did not recognize the ship class, it fell back to a default ship and overwrote your actual stats. Upgrades now increment your current stat value directly, which is simpler and correct regardless of class lookup.

## Turn Reset Clock

The turn reset countdown was showing up to 24 hours in some cases instead of the correct maximum of 4 hours. The app-side calculation was using a midnight UTC boundary that was never updated when the game switched to 4-hour reset cycles. It now matches the backend.

## Planet Production

The collection button was occasionally showing "Check back in 1 hours" when production was ready or nearly ready. The backend now respects the production ready flag as the primary gate, and the time display shows minutes when under an hour.
