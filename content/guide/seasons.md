---
title: "Seasons & Leaderboard"
date: 2026-02-28
draft: false
description: "How seasons work, scoring, and what happens when a season ends"
weight: 11
toc: true
---

Big Bang Smugglers is played in **seasons**: time-limited campaigns where players compete in a fresh galaxy. When a season ends, standings are recorded, the galaxy closes, and a new one opens.

## How Seasons Work

Each season takes place in a **newly generated galaxy**. Everything resets: sectors, ports, planets, NPC positions, trade prices. You carry nothing in from the previous season.

**Season lifecycle:**
1. **Generation**: Admin creates a new galaxy, feed notifies all players ("The Big Bang has started!")
2. **Active**: Players join, explore, trade, fight, build. Full gameplay.
3. **Countdown**: A `season_ending` feed notification fires when the end date is approaching
4. **End**: Season closes, winners recorded, galaxy locked
5. **Records**: Final standings written to season history

**Default season length:** 30 days (configurable per season).

## Joining a Season

When a new season opens, you'll see it in the **Leaderboard / Season** screen. Tap **Join** to enter the galaxy.

You can participate in multiple concurrent seasons if the server is running more than one simultaneously.

## Scoring & Leaderboard

The leaderboard ranks players by **XP earned** during the season. Tiebreaker: total credits earned.

**How to earn XP:**
- Trading (buy and sell transactions)
- Completing missions
- Winning combat
- Claiming and developing planets
- Exploring new sectors

The Leaderboard screen shows:
- Your current rank in the active season
- Top players and their scores
- Overall all-time leaderboard across all seasons

Leaderboard updates in real time as players earn XP.

## Season End

When a season ends:
- **Your standing is locked**: final rank recorded to season history
- **Galaxy closes**: you're removed from the galaxy, ship and assets reset
- **Credits and ships reset**: you start fresh in the next season
- **Season record persists**: your final rank is part of your permanent history

The feed notifies you via a `season_ending` message before the close, giving you time to finish trades, collect planet production, and make your final moves.

## New Season Strategy

Since every season is a fresh start, early-season decisions matter a lot:

1. **Explore fast**: sectors you haven't visited can't be warped to; cover ground early to build your warp network
2. **Find the trade routes**: price bands are randomized per galaxy; scout ports before committing to a route
3. **Planet early**: planets compound over time; claiming and developing one in the first few days pays off for the rest of the season
4. **Mission stacking**: missions give early XP boosts; run them alongside trade routes for efficient turns

## Season Records

Your final standings from each season are stored permanently. Over time this builds a career record: a history of how you've performed across the galaxy's lifetimes.
