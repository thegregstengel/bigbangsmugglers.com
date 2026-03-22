---
title: "v1.9.5 — NPC & Bounty Stability Update"
date: 2026-03-22T19:25:00-04:00
type: blog
description: "v1.9.5 fixes attack flow wiring, federation scan/bribe errors, corp withdrawal policy handling, bounty service auth guards, and fully wires trading and research stations into gameplay."
---

v1.9.5 is a stabilization update for the new NPC engagement and faction bounty systems, plus a long-overdue wiring fix for stations.

This release focuses on making the systems introduced in the recent major updates work reliably in live gameplay.

## NPC Combat Button Fixes

Several attack buttons in the new NPC interaction flows were sending the wrong parameters to combat initiation.

This prevented combat from resolving correctly from multiple modal paths. The wiring is now corrected across the affected NPC interaction screens.

## Federation Scan and Bribe Fixes

Federation scan and bribe actions could fail with incorrect errors because sector validation was reading from the wrong location.

That validation now reads sector information from the ship record instead of a non-existent player document field.

## Corp Withdrawal Policy Fix

Corporation bank withdrawals could be blocked even when policy allowed them.

This release fixes that permission path so enabled withdrawal rules behave the way they are supposed to.

## Bounty Service Auth Hardening

Several bounty-related service functions were missing proper auth guards.

Those protections are now in place, improving reliability and reducing bad request paths in the bounty system.

## Trading and Research Stations Now Fully Wired

Trading and research station UI existed, but parts of the flow were still stubbed instead of connected to the real screens.

This update wires those existing station screens into the live navigation flow, turning them into working gameplay paths instead of placeholders.

## Overall

v1.9.5 is about turning major recent systems into something more solid and dependable. Combat entry points are now correctly wired, faction interaction errors are fixed, bounty services are safer, corporation policy behavior is more consistent, and stations are more fully integrated into the actual game flow.
