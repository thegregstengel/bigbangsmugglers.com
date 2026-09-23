---
title: "Getting Started"
date: 2026-08-04
description: "Sign up, join a season, and spend your first 250 turns well"
weight: 10
group: start
tags: [platform, seasons]
changed_in: []
stats:
  - { label: "Turns", value: "250", sub: "full reset every 4 hours" }
  - { label: "Wallet", value: "5,000 cr", sub: "to start" }
  - { label: "Handle", value: "3–20", sub: "characters" }
---

## Get the game

- **Android**: Google Play.
- **Web**: [play.bigbangsmugglers.com](https://play.bigbangsmugglers.com) — no
  invite code, no download.

Sign in with **email and password** (you must verify the address before you
can play) or **Google**. Then pick a captain handle: 3 to 20 characters,
letters, numbers and spaces only. Runs of spaces collapse to one. You can
rename yourself later — but renames carry a cooldown and post a public feed
story connecting the old name to the new one, so a handle is not a disguise.

There is no class to pick and no faction to choose. Everyone starts neutral.
What you become is decided by what you do.

## Join a season

Big Bang Smugglers is played in **seasons**. A season is a freshly generated
galaxy with a fixed player cap and an end date, and it is the only container
for anything you own. Browse seasons from the Settings tab.

Three rules worth knowing before you tap Join:

1. **One season at a time.** You cannot be enrolled in two.
2. **Leaving is permanent.** Leave a season and you can never rejoin *that*
   season — the server refuses with `ALREADY_PARTICIPATED`. Everything you
   held there is gone.
3. **A full season is closed.** Seasons have a hard player cap, and joining
   fails once it's reached.

If you lead a corporation with other members in it, you must hand leadership
over before you can leave.

### What you start with

| | |
|---|---|
| Wallet | 5,000 cr |
| Bank | 0 |
| Turns | A full tank — 250 resetting every 4 hours on the default settings |
| Alignment | 0 (True Neutral) |
| Location | Sector 0 — the Stardock, the safest place in the galaxy |
| Ship | SS Starter |

The **SS Starter**: 20 holds, 15 shields, **40 hull**, no fighters, no
torpedoes, 30% escape. It is a delivery van with a radio. It cannot win a
fight and it is not supposed to.

## Turns

A turn is the unit of action. Moving one sector costs 1. Buying or selling
cargo costs 1, however many units you move. Fighting costs 1.

**Turns reset in full every 4 hours**, on the UTC boundaries: 00:00, 04:00,
08:00, 12:00, 16:00 and 20:00. The reset is a *reset*, not a top-up — you go
back to 250 whether you had 3 left or 240. **Turns never carry over.** That
is doctrine, not a tuning knob: banking turns is not a strategy in this game.

Cycle length and the turn cap are season configuration. Today's defaults are
4 hours and 250 turns; the game always shows you the live figures and the
countdown to the next reset.

You can buy extra turns — see [Provisions](/guide/gameplay/#buying-turns) —
but only 5 per cycle, at 800 cr each.

## Your first cycle

You start with a full tank of 250 turns and the reset clock already running.
Here is how to spend them.

You are in Sector 0, standing on the Stardock: the deepest market in the
galaxy, a shipyard, a bank, repair, recruitment, defense contracts and a
supply shop, all in one sector. It is also permanently PvP-free.

**1. Decide about the Frontier Scout.**
The classic opening: the Frontier Scout is a tier-1 balanced hull at
**5,000 cr** — your entire bankroll. 40 holds against the Starter's 20, 150
shields against 15, 100 hull against 40, real fighters and torpedoes, and a
50% escape chance. Buying it leaves you broke with a real ship. Not buying it
leaves you with capital and a hull that dies to a stiff breeze.

Either works. The Scout pays for itself inside an hour of trading, and the
Starter's 20 holds throttle everything you do. Most captains buy.

**2. Look at prices before you buy cargo.**
Prices are not fixed in 2.0. Every port has an anchor price per commodity and
the live stock level swings it by up to ±28%. A port that just got emptied
charges a premium; a port you just flooded pays less. The port screen quotes
your actual per-unit price, tax and fee before you commit.

**3. Buy where a port specializes.**
Every commodity has a specialist that sells it cheapest — that ordering is
enforced by the game's own catalog validation. Fuel Depots are the cheap fuel
(anchor 90). Agricultural Ports are the cheap organics (75). Tech and
Research Ports are the cheap equipment (375 and 350). The Stardock is deep
and convenient but it is not cheap.

**4. Sell where the anchor is high.**
Organics bought at an agri port at ~75 sell at a mining port whose organics
anchor is 240. That's the whole game in one sentence. Equipment carries
**2 volume per unit**, so a hold full of equipment is half as many units as a
hold full of fuel — factor that into every route.

**5. Move, and expect company.**
Each move to a linked sector is 1 turn. Entering a sector can trigger sector
hazards, mines somebody left, and NPC encounters. Federation space is quiet;
it gets louder the further out you go.

**6. Bank what you can't afford to lose.**
Your **wallet** is what gets looted when you lose a fight, robbed on a
planet, or fined by customs. Your **bank** is never touched by any of it.
Banking is free and instant, but **you must be docked at a port with a bank
teller** — the three starports and Federation Ports. You are standing on one
right now; use it before you fly somewhere dangerous.

## What changed from 1.x

If you played the old game, these will bite you:

- **Prices move.** The fixed price table is gone. Stock swings prices ±28%
  and heavy trading at one port stacks pressure on top, up to ×2.
- **Ports restock.** Every 4-hour tick pulls a port's stock back toward its
  baseline. Scarcity is real but temporary.
- **Cargo is pooled, not lotted.** One stack per commodity with a weighted
  average cost basis. One sell is one turn regardless of how you acquired it.
- **Ships have hull.** Shields absorb first; overflow spills to hull at ×1.5.
  Hull 0 is the only way a ship dies, and hull never regenerates — only port
  repair brings it back.
- **The disabled state is deleted.** No disabled ships, no field kits, no
  auto-recovery. You either survive damaged or you're in a pod.
- **Reputation is gone; standing replaced it.** Trader reputation is now
  Merchant Guild standing. Alignment and standing are two different axes.
- **PvP is classified by your alignment**, at ±300 — not by what hull you fly.
- **Three starports, not two**: the Stardock at Sector 0, the Pirate Haven in
  the middle of the pirate band, and the Merchant Exchange out in the middle
  ring.
- **45 purchasable hulls** across three lines, plus six earn-only epics.
- **Repair no longer refills your munitions.** Fighters and torpedoes are
  bought back separately at the restock bay.
- **Missions have no accept step and no cap.** You are enrolled lazily; your
  progress accrues whether or not you opened the screen.

## Where to go next

- Making money: [Trading & the Market](/guide/trading/)
- Getting around: [Navigation & Travel](/guide/navigation/)
- Not dying: [Combat](/guide/combat/)
- Picking a side: [Factions, Alignment & Standing](/guide/reputation-factions/)
