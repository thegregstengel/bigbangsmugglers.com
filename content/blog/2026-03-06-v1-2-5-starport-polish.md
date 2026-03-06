---
title: "v1.2.6 — Starport Polish & Ship Stats"
date: 2026-03-06T14:00:00
description: "Version 1.2.6 overhauls the starport shipyard, fixes ship repair, corrects stat display across the ship screen, and fixes the turn reset clock."
---

Version 1.2.6 is a polish pass on the starport and ship screen, fixing a cluster of display and behavior bugs reported by players.

## Shipyard Overhaul

The shipyard now shows fighters, torpedoes, and cargo holds as separate cards, each with a consistent layout: your current count, the maximum you can reach with upgrades, and a buy button with the cost shown inline. If a stat is fully upgraded the buy button is replaced with a confirmation so you know you have hit the ceiling.

Repair now restores all combat stats. Previously, the repair backend only topped up shields on a functional ship and left fighters and torpedoes at whatever damaged value they were at. The repair cost calculation has also been corrected to account for total damage across all three stats rather than shields alone. The button is now simply labeled "Repair Ship."

## Ship Stats Display

The ship screen stat cards now show consistent information across all four stats. Holds displays your current hold count with the maximum you can reach through upgrades underneath, matching the format used by fighters, torpedoes, and shields. The previous display was showing cargo used versus cargo capacity, which belongs in the cargo section below.

Fighters and torpedoes now correctly show the repair maximum alongside the upgrade ceiling so you always know both where you are and how far you can go.

## Repair Button Visibility

The repair button no longer appears when your ship is in full health. Previously, ships with zero base fighters or torpedoes (scouts, freighters, and most trading vessels) always showed the repair button because the fallback maximum was hardcoded to 100, making zero fighters look like damage. The repair section now only appears when there is actually something to repair.

## Cargo Hold Upgrades

Upgrading cargo holds no longer resets your hold count to a wrong value. The upgrade system was recalculating all ship stats from the ship class definition after every purchase. If the backend did not recognize the ship class, it fell back to a default ship and overwrote your actual stats. Upgrades now increment your current stat value directly, which is simpler and correct regardless of class lookup.

## Turn Reset Clock

The turn reset countdown was showing up to 24 hours in some cases instead of the correct maximum of 4 hours. The app-side calculation was using a midnight UTC boundary that was never updated when the game switched to 4-hour reset cycles. It now matches the backend.

## Planet Production

The collection button was occasionally showing "Check back in 1 hours" when production was ready or nearly ready. The backend now respects the production ready flag as the primary gate, and the time display shows minutes when under an hour.
