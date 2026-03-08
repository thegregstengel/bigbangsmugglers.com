---
title: "v1.1.0 — Bounties, Trading Posts, and the Web Version"
date: 2026-03-01T10:00:00
description: "Version 1.1.0 ships the bounty system, player-built trading posts, past season history, and a round of stability fixes."
---

Version 1.1.0 is a major feature release. Three new systems and a new way to play.

## Bounty System

Players can now post bounties on other players from any tavern. Set a credit reward, and it goes live in the galaxy. When another player takes down the target, the bounty pays out automatically. Collections show up in the feed, so the galaxy knows when a contract is settled.

## Player-Built Trading Posts

Planet owners can now construct a trading post on their planet. Trading posts sell commodities to passing players at competitive prices, and the owner earns a percentage of every sale. Build from your planet screen once you have a Warehouse at level 2. Upgrade the post over time to increase stock capacity and revenue. Other players can attempt to rob your trading post, so a strong garrison matters.

## Past Seasons

The Feed screen has a new Past Seasons tab. Completed galaxies are archived with final standings so you can look back at how previous seasons played out.

## Bug Fixes

- Turn reset display now shows the correct countdown to the next 4-hour boundary
- Auto-repair at turn reset now fires correctly when the player opens the ship screen
- Production ticks aligned to 4-hour UTC boundaries, matching turn and repair resets
- Planet production correctly resets the ready flag after collection so the next tick fires
- NPC combat feed no longer leaks private battle results to other players in the galaxy
- Ship upgrade sync fixed -- holds, shields, fighters, and torps all update correctly after purchase
- Pirate ports no longer offer standard trading services
