---
title: "v2.0.8 — Standing Restored"
date: 2026-08-04T00:00:00Z
type: blog
description: "Standing gains from clean scans and missions, single-run galaxy ticks, and fixes across trading, ships, planets and combat."
kind: release
version: 2.0.8
tags: [factions, planets, combat, trading]
---

Changelog for v2.0.8.

## Standing

- Clean customs scans now award standing, with an on-screen confirmation.
- Daily, seasonal and ad-hoc missions carry standing rewards (lawful positive, underworld negative).
- Surviving a pirate ambush awards defensive standing.
- Warp arrivals surface patrol inspections; previously the contact expired unused.

## World tick

- The four-hour cycle ran twice per boundary. Port upkeep, delinquency accrual and market restock were applied twice each cycle; now applied once. The backup trigger remains in place.

## Trading and ships

- Cargo could not be sold while carrying contraband of the same commodity.
- Ship capacity upgrades (holds, shields, fighters, torpedoes) were unreachable from the starport.
- Hull repair was unavailable when shields were full; repair results now report actual restoration.
- Ship rename reported failure on success.
- Restock, rename and upgrade prices now come from the server catalog.
- Repairs no longer refill fighters and torpedoes; munitions come from restock.

## Planets and stations

- Planet ownership checks failed for all owners; owner-only features were unreachable.
- Garrison staffing, starbase construction and trading posts were not connected to the current backend.
- Trading post income was accruing with no way to collect it.
- Planet rename and corp-internal deed transfer added.

## Combat

- Defense contracts no longer permit attacking while protected.
- A lost fleet strike no longer overwrites a purchased contract.
- Fleet kills apply the same alignment, statistics and immunity consequences as solo kills.
- Respawn protection applies after every death.
- Named NPCs retain damage between engagements and regenerate over time.
- Losing an engagement no longer awards experience.

## Progression

- Player level is derived from the season curve at every write path.
- Mission completions count toward the missions leaderboard.
- Event progress accrues without opening the Events screen.
- Maximum-tier scanners reported empty sectors.
- Starting sector is marked visited on join.
- Provisions charge only for turns delivered; cloaks last a fixed duration.

## Other

- Economy pricing corrections.
- Security hardening across the API and live connections.
- Leaderboards no longer expose exact player balances.

Migrations: galaxy tick boundary claims, ban revocation notifications.
