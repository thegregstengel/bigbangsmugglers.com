---
title: "v1.9.6 — Bounty & NPC Follow-Up Fixes"
date: 2026-03-22T21:50:00-04:00
type: blog
description: "v1.9.6 fixes pirate spawns in Federation space, adds sector validation to remaining NPC interaction functions, and ensures the Wanted HUD updates correctly after bounty generation."
---

v1.9.6 is a focused follow-up patch for the new NPC engagement and faction bounty systems.

This release cleans up a few important edge cases found after the broader bounty and interaction overhaul shipped.

## Pirates No Longer Spawn in Federation Territory

Pirates were still able to appear in Federation-controlled space under some conditions.

That behavior is now fixed so Federation territory behaves the way the region rules intend.

## Sector Validation Added to Remaining NPC Interaction Functions

Four remaining NPC interaction paths were still missing proper sector validation.

This release closes those gaps so NPC actions consistently verify that the target is actually valid for the player's current sector context.

## Wanted HUD Now Updates Correctly

The Wanted card on the Ship screen could fail to appear immediately after bounty generation.

That display path is now fixed so bounty state is reflected more reliably in the UI.

## Overall

v1.9.6 is a cleanup and consistency release. It reinforces the intended rules for faction territory, tightens NPC interaction validation, and makes wanted-state feedback more dependable after the recent bounty system rollout.
