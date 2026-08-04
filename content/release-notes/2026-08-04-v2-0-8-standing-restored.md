---
title: "v2.0.8 — Standing Restored"
date: 2026-08-04T00:00:00Z
type: blog
description: "Standing finally rises for lawful play, the galaxy tick stops charging you twice, and the shops, stations and planets all work — the biggest fix release since launch."
---

We spent a day playing our own game from the outside — thousands of real actions against the live servers — and then had every line of it reviewed. This is what came back.

## Your Standing Works Now

If you've been flying clean and wondering why your standing never moved: it genuinely never moved. A clean customs scan wrote nothing at all — as far as the galaxy was concerned, you'd never been scanned. Warping into a patrol contact silently dropped the inspection. Fighting off a pirate that jumped *you* paid nothing.

All of it is fixed:

- **Clean scans pay.** Pass an inspection with an honest hold and your standing rises, with a confirmation so you can see it happen.
- **Missions pay.** Daily and seasonal contracts now carry standing rewards — lawful work raises you, underworld work lowers you. A captain running honest dailies can reach Federation standing inside a week.
- **Self-defense counts.** Surviving a pirate ambush now earns what it always should have.
- **Warp arrivals** no longer swallow the inspection.

## The Galaxy Was Charging You Twice

Every four-hour cycle was running **twice**, five minutes apart. Port upkeep was billed double, delinquency grace was effectively halved, and market restock ran twice. It now runs exactly once — while keeping the backup that guarantees it runs at all.

## Everything in the Shops Works

Trading while carrying contraband (you couldn't sell clean cargo at all), ship capacity upgrades, hull repairs, planet ownership and its whole starbase and garrison chain, trading posts and their income — all fixed.

## Combat Is Fairer

- A defense contract can no longer be used as cover to attack from
- Losing a fleet strike no longer destroys the contract you paid for
- Fleet kills carry the same consequences as solo kills
- Everyone gets respawn protection after any death, not just some deaths
- Named NPCs now carry their wounds between fights — bosses can be worn down
- Losing a fight no longer pays experience

## Under the Hood

Level calculations are consistent everywhere, mission completions actually count toward the leaderboard, event progress accrues whether or not you open the Events screen, and the top-tier scanner no longer reports empty space where there's a galaxy. Plus a round of security hardening across the API and live connections.

Android: version 2.0.8 is rolling out on Google Play. Web players are already on it.

Thanks to the captains filing reports. You keep finding the things we can't.
