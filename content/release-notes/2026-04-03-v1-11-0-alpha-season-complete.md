---
title: "v1.11.0 — Alpha Season Complete"
date: 2026-04-03T12:00:00-04:00
type: blog
description: "v1.11.0 closes the first alpha season with season-end recap, trader reputation pricing, in-app notifications, feed reactions, player feedback, and infrastructure fixes."
---

Big Bang Smugglers v1.11.0 closes out the first alpha season and hands the ship over to beta. Here is what changed.

## Season End Recap

When a season ends, you now see a full recap before returning to the lobby. The recap screen shows your final stats — credits, XP, kills, missions completed, planets owned, sectors explored, streak, and more — alongside the top finishers in each category. You can see who walked away as Richest Captain, Top Bounty Hunter, Mission Master, Planet Baron, and more.

After you acknowledge the recap, your season data is preserved. Season records are archived to cloud storage before the galaxy is wiped, so historical leaderboards and stats are kept permanently.

## Season Countdown Push Alerts

You will now receive push notifications as a season approaches its end. Alerts fire at milestone intervals so you have time to make your final moves, settle debts, and fight for your leaderboard position before the season closes.

## In-App Notification System

Critical alerts now appear inside the app without requiring a feed check. Mission completions, admin broadcasts, and urgent game events surface as modal popups or toast banners depending on priority. You can dismiss them and keep playing.

## Trader Reputation and Faction Pricing

Every port in the galaxy now prices you based on two independent reputation scores:

**Trader Reputation** applies everywhere. You start at neutral (50). Killing NPC traders drops your score. A low trader reputation means a surcharge at every port in the galaxy — up to 10% above base prices. A high score earns you a modest discount. Your current trader reputation is visible in your Faction Info panel.

**Faction Alignment** applies at faction-controlled ports. Federation ports reward positive alignment with up to 20% off and punish hostile players with up to 50% markups. Pirate ports work the same in reverse. These two multipliers stack.

The Confirm Purchase modal now shows you the breakdown — base price, faction modifier, and trader reputation modifier — so you always know why you are paying what you are paying.

## Feed Reactions

You can now react to events in the galaxy feed. Five reactions are available on each feed item:

- 🔥 Great
- 😬 Not great
- 🫣 Embarrassed
- 👍 Upvote
- 👎 Downvote

Reaction counts are visible to everyone. Your active reactions are highlighted.

## Player Feedback Form

A feedback form is now available in Settings. Use it to report bugs, request features, or leave general impressions. Submissions go directly to the development team.

## Bug Fixes and Infrastructure

- Season-end lifecycle consolidated and stabilized across all edge cases
- Season countdown warnings corrected
- Scan Sector now returns instant results with enriched sector data
- Stealth Reconnaissance removed (was non-functional)
- Deployables scan now deducts turns and shows results in a modal
- TypeScript errors resolved across 21 app files
