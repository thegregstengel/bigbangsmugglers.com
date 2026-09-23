---
title: "v1.23.0 — Events, Roles, End-game, and New Player Onboarding"
date: 2026-07-05T00:00:00Z
type: blog
description: "v1.23.0 launches a live daily events system, a role specialization tree, cross-season prestige tiers, season end-game recaps, and a three-phase new-player onboarding flow, alongside 80+ bug fixes and balance changes."
entry: release
version: 1.23.0
tags: [progression, missions, seasons, smuggling]
---

v1.23.0 is the biggest content release since the game launched. Daily events, role specialization, prestige tiers, a full season end-game, and new-player onboarding are all live. An extensive bug-fix and balance pass ships alongside them — over 80 issues closed.

## Daily Events

A live events system now runs inside every galaxy. Daily events generate automatically from a rotating template slate and are visible from the Events board on your Ship screen.

Events have typed objectives, defined reward types — XP, credits, or special items — and expiry windows. Faction standing gates which events each player can access; two players in the same sector may see a different slate. Bounty events let you hunt specific targets for outsized payouts. Once an event's objectives are complete, you claim rewards directly from the board.

Special event items equip directly to your ship and feed passive stat bonuses into your hull in real time. The first two permanent equip items now have their final locked stat values.

## Role Specialization and Prestige

Roles now branch into a specialization tree. As your role level climbs, you unlock passive stat perks tied to your career path — a combat-heavy run plays differently at high role level than a trade-focused one.

The Trader role was previously dormant: trade counts were not accumulating. That is fixed. Trade counts now accumulate correctly and feed role-level progression.

Cross-season prestige tiers are cosmetic milestones. Hit a lifetime XP threshold and you carry a permanent title into every future galaxy.

## Season End-game

When a galaxy closes, you now receive a narrative recap of your season with winner awards distributed at the close. The winner is determined by a single canonical metric — XP earned, with credits as tiebreak.

Countdown warnings go out as the season timer approaches zero, giving you time to make final moves rather than discovering the galaxy ended while you were away.

## New Player Onboarding

Three new features reduce the new-player cliff significantly.

A contextual glossary of core mechanics is accessible from the Help button anywhere in the app. Tap any highlighted term to see a definition inline; ⓘ tip badges throughout the UI deep-link directly to the relevant glossary entry.

A "What Now?" card on the Nav screen recommends your next best action based on your current state — turns remaining, missions pending, sector opportunities — and updates as you progress.

A guided checklist walks you through your first session: warp to your first sector, complete your first trade, deploy your first device. The checklist lives on the Nav tab and clears automatically.

"While You Were Away" shows a re-entry summary when you return after extended downtime — what moved, what expired, what changed while you were offline.

Post-combat now shows a richer consequence summary so you understand exactly what you lost or gained from the engagement before you move on.

## Dead-end Sectors

The galaxy generator now occasionally produces single-access sectors — pockets with only one way in or out. These dead-ends are high-risk, high-reward locations that change how you plan a run through that region of the map.

The old one-way link mechanic is retired. All sector links are now undirected and reciprocal.

## Corporations

Corp invites are live. Send a direct invitation from the Corp screen; invitees see incoming invites in their own Corp screen inbox.

Corp management works correctly: approve join requests, kick members (with de-affiliation), and transfer leadership. The Leave button is fixed — corp founders are no longer trapped. Corp Leaders and Officers can now upgrade corp-owned planet structures directly.

## Faction Standing

Faction alignment now does real mechanical work across three systems:

High standing with your faction grants a combat bonus against opposing-faction targets. Low standing triggers automatic bounty aggression from NPC patrols during warp hops. Standing also gates access to certain missions — some runs require a minimum relationship with the faction before the mission appears in your list.

Trade Bonus has been relabeled as a faction service discount, which is what it actually provides.

## Economy

The price curve has been rebuilt around band normalization. Prices stay stable within their expected band and resist the runaway extremes that emerged in long-running galaxies, where a commodity's price could drift far outside its intended range.

Boosters now apply consistently across all income types. Credit boosters hit trade sale proceeds. XP and credit boosters apply to warp gains, landmark discoveries, and auto-mission completion — not just the event loop where they were previously confined.

## Player Trading Post Combat

Other players can now attack your trading posts. Successful attacks have real consequences for the post owner. When your post is hit, the galaxy funds a system grudge bounty on the attacker, creating a persistent incentive to pursue them. Defending your post is now part of the trading-post game.

## Security

Server-side authorization has been hardened across several actions that previously relied on client-side validation only. No player-facing behavior changes; the rules that already existed in the UI are now enforced at the server.

## Contraband and Smuggling

Contraband detection and valuation are now consistent across all buy and sell flows. Getting caught in a detected sale has real consequences — the free retry path is gone. Black Tech fences at a genuine premium, making the risk-reward meaningful.

The fictional "Est. sell value" hints in the black market buy confirm have been removed; entry-scan copy and sale-time copy are now distinct and accurate. NPC patrols auto-scan your cargo when you move through their sector.

## Other Fixes

- Information Broker at ports now works and aligns with the pricing backend.
- Reputation-adjusted pricing applies consistently across intel, warp, StarNav, weapons, supplies, and shipyard tiers — what the UI shows matches what you are charged.
- Shield Booster now grants +15% of your maximum shields, not your current damaged HP.
- PvP escape immunity now correctly goes to the escapee.
- Corp-mates no longer trigger each other's mines or sector defenses.
- 1v1 PvP now transfers cargo to the winner.
- Fleet kills deposit captured cargo to the corp Starbase.
- Bounties now collect when a defender wins PvP or a fleet eliminates a target.
- StarNav scanner shows real player counts with tier-gated hostile indicators.
- Sector hazards are populated and apply on all travel, not only manual warp.
- Ion storms drift between sectors each tick.
- Deployable decay runs on schedule.
- Landmark jumps use the actual generated galaxy size for their distance calculation.
- Planet claim costs, export income, and Trading Post stock come from the backend source of truth.
- Capturing a planet now transfers the Trading Post's port ownership.
- The sector graph is memoized inside the warp transaction.
- NPC modal odds, prices, and bounty hints match live backend values.
- Change Password is wired to a real reset email.
- Sector favorites and notes are available from the Nav screen for quick recall.
- Smart warnings now appear before you sell contraband or abandon a timed action.
