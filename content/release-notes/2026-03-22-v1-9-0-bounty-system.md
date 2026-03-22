---
title: "v1.9.0 — NPC Engagement & Faction Bounty System"
date: 2026-03-22T12:55:00-04:00
type: blog
description: "v1.9.0 adds a full NPC engagement overhaul, faction bounties, wanted status, contract offices, and much richer faction consequences."
---

v1.9.0 is a major NPC interaction and bounty system update.

This release changes NPC encounters from simple combat triggers into a more dynamic system with clearer player choice, faction consequences, bounty hunting, wanted status, and smarter interaction flows.

## NPC Engage Modal Rework

NPC encounters now use a cleaner engagement model with a single **Engage** button and type-specific options.

This makes encounters easier to understand and puts the costs and consequences up front instead of hiding them behind inconsistent flows.

## Faction Bounty System

Attacking faction-aligned NPCs now has real consequences.

New behavior includes:

- automatic bounty generation when attacking federation or pirate-aligned NPCs
- bounty values that scale with kills and NPC tier
- faction-specific bounty systems instead of a generic punishment layer

## Contract Offices

Faction starports now include contract offices:

- **Federation Bounty Registry**
- **Pirate Bay Contract Office**

These give bounty gameplay a real location and turn bounty resolution into part of world navigation instead of an invisible mechanic.

## Player Bounty Collection

Bounty hunting is now a two-step process:

1. defeat the target in PvP
2. travel to the correct contract office to collect the claim

That makes bounty play feel like an actual loop instead of an instant payout.

## Smarter NPC Interaction Rules

Different NPC types now behave differently:

### Federation patrols
- Scan / Bribe / Jettison / Attack
- patrols are only aggressive when you actually have a bounty

### Pirates
- Surrender / Bribe / Jettison / Attack
- bounty hunters get a more hostile interaction path

### Traders
- Trade / Rob / Attack
- traders never auto-popup and remain player-initiated interactions

## Wanted Status HUD

The Ship Stats tab now shows a visible **WANTED** HUD state when active bounties exist.

This makes risk and faction heat visible instead of hidden in backend state.

## Port Restrictions and Payoff Flow

Faction consequences now affect travel and access.

This includes:

- arrest behavior at opposing faction starports
- alignment-based access denial
- bounty payoff at the correct contract office
- travel pressure when trying to clear wanted status

## Bounty Feed Notifications

Bounty events now appear in the feed with useful context, including "last seen" style intel.

That makes the system feel alive and gives players better situational awareness.

Overall, v1.9.0 makes the galaxy feel far more reactive. NPCs now behave more distinctly, factions remember what you do, and criminal behavior has meaningful consequences and rewards.
