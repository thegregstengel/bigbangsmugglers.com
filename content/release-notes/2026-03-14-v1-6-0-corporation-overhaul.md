---
title: "v1.6.0 — Corporation Overhaul"
date: 2026-03-14T20:00:00
type: blog
description: "v1.6.0 is a major corporation update — real-time sync, join policies, dynamic sizing, leader titles, and bug fixes throughout."
---

v1.6.0 is a major overhaul of the corporation system, fixing several long-standing bugs and adding new mechanics for how corps are managed and joined.

## Bug Fixes

Corporation names were not appearing on planet info screens or public player profiles due to a data path mismatch. Corp leader status was also not being recognized correctly when managing corp-owned planets, meaning leaders couldn't perform certain management actions. Both issues are fixed.

## Real-Time Corporation Sync

Corporation data now updates in real-time across all screens via a live Firestore listener. Previously, corp membership and role information could be stale until you refreshed. Now your corp status, member list, and recent activity sync instantly without needing to reload.

## Join Policies

Corps now have three join modes, set at creation and changeable by the leader:

- **Open** — anyone can join immediately (previous behavior)
- **Request** — players submit a join request; the leader approves or denies
- **Invite Only** — members can only join by direct invitation from the leader

## Dynamic Corp Sizing

Corp size limits are now calculated from the galaxy's player cap rather than a hardcoded number. Smaller galaxies have smaller corps, keeping the balance intact. A 25-player galaxy caps corps at around 3 members; a 100-player galaxy allows up to 10.

## Alignment-Based Leader Titles

Corp leader titles now reflect faction alignment. Federation-aligned leaders carry Federation titles, pirate-aligned leaders carry pirate titles, and neutral leaders get their own distinct title. The title appears wherever your corp role is shown.

## Corp Name in Profiles

Your corporation name now appears in your player stats card in Settings and on your public profile visible to other players on the leaderboard.
