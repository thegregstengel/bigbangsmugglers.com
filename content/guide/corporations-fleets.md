---
title: "Corporations & Fleets"
date: 2026-07-02
draft: false
description: "Player corporations — shared bank, chat, ship pool, corp planets, and fleet combat"
weight: 18
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

A corporation is your crew for the season. Solo captains can trade, fight, and build planets just fine — but a corp adds things you cannot get alone: a private chat channel, a communal credit bank, a shared ship pool, corp-affiliated planets your whole crew can use, protection from direct PvP between members, and fleets — the only way in the game to bring more than one ship to a fight.

Corporations are scoped to a single galaxy and season. When the season ends, the corp — bank balance included — is deleted. Plan accordingly (see [The Corp Bank](#the-corp-bank)).

## Why Join a Corporation

| Benefit | What you get |
|---------|--------------|
| Corp chat | Private channel, members only, separate from the galaxy feed |
| Corp bank | Communal credit pool anyone can pay into |
| Ship pool | Donate spare ships to the corp; any member can claim one |
| Corp planets | Land, park, and use storage on every planet your corp-mates own |
| Corp Starbase | Shared hangar, ship pool, and a vault for corp assets |
| Fleets | Up to 3 corp-mates attack one target as a single combined force |
| Friendly-fire protection | Corp-mates cannot attack each other in direct PvP |
| Corp leaderboard | Your corp competes as a unit in the Feed tab leaderboards |

## Creating a Corporation

Go to the **Ship** tab → **Corps** in-screen tab. If you are not in a corp, you will see the corporation browser and a Create Corporation card.

- **Cost: 50,000 credits.** Paid from your wallet if it covers the full amount; otherwise the whole cost comes from your personal bank.
- **Name:** up to 30 characters, unique within the galaxy. Names that differ only in punctuation or capitalization count as the same name.
- **Alignment:** pick Federation, Pirate, or Independent.
- **Join policy:** pick Open, Request, or Invite Only (you can change this later).
- You must be in a galaxy, and you can only belong to one corp at a time.

**Size cap:** corp size scales with the season's player cap — one member slot per 10 player slots, with a minimum of 3. A 60-player galaxy allows 6-member corps; a 100-player galaxy allows 10. The cap is fixed at creation, so bigger galaxies allow bigger corps.

The creator becomes the corp's **Leader**. Read [A Warning for Founders](#a-warning-for-founders) before you tap Create.

## Joining a Corporation

Browse corps from **Ship → Corps**. Each row shows the name, alignment, member count, and join policy. Tap a corp to join.

- **Open:** you join instantly as a Member.
- **Request:** your tap files a join request. A Leader or Officer approves or rejects it. **Important:** approval does not add you automatically — once approved, return to the browser and tap the corp again to complete the join. Approval also does not reserve a slot, so a corp that fills up in the meantime will still turn you away.
- **Invite Only:** joining requires a standing invitation, and there is currently no way to send one from the app. If you are setting a join policy for your own corp, use **Open** or **Request** — an Invite Only corp cannot grow.

Joining tags every planet you own with your new corp, and leaving removes the tag.

## Roles & Permissions

Three roles: **Leader**, **Officer**, **Member**. What each can do:

| Action | Leader | Officer | Member |
|--------|--------|---------|--------|
| Promote (Member → Officer) / demote | Yes | — | — |
| Change join policy | Yes | — | — |
| Kick members | Anyone but themselves | Members only (not other Officers) | — |
| Approve / reject join requests | Yes | Yes | — |
| Set corp policies | Yes | — | — |
| Deposit to the corp bank | Yes | Yes | Yes |
| Withdraw from the corp bank | Yes | Yes | Only if the bank-spend policy is on |
| Corp chat, ship pool, fleets | Yes | Yes | Yes |

The one policy toggle that matters is **"Members can withdraw"** — it controls whether ordinary Members can pull credits from the corp bank. Leaders and Officers can always withdraw.

## The Corp Bank

Any member can deposit credits from their **wallet** (not their personal bank) into the corp pool, up to 10,000,000 per transaction. Withdrawals go back to your wallet and follow the permission table above. Every deposit and withdrawal is recorded in the corp activity log.

The bank has one automatic inflow besides deposits: **credit loot from fleet victories** lands here (see [Fleet Loot](#fleet-loot)).

**The corp bank is wiped with the corp at season end.** Nothing is refunded or carried over. Withdraw and distribute the balance before the season closes — treat the last days of a season as payout time.

## Corp Chat

Every corp has a private chat channel in the Corps tab, visible to members only and separate from the public galaxy feed. Messages are capped at 500 characters with a 3-second cooldown between sends, and the app shows the last 50 messages.

## The Ship Pool

The ship pool turns your corp's spare hulls into a shared garage. It lives at your **corp Starbase** (see below), and both ends of the exchange happen there:

- **Donate:** fly to the corp Starbase's sector and donate any ship you own that is not your active ship. The ship converts to a stored spec — class, tier, holds, shields, fighters, torpedoes, upgrades, warp drive, and StarNav are all preserved. Any cargo aboard is deleted, so empty it first.
- **Claim:** any member standing in the Starbase's sector can claim a pooled ship. It arrives in your hangar **inactive and empty** — you still have to switch to it before flying it.

This is the fastest way to get a corp-mate who just lost a ship back into a real hull.

## Corp Planets & the Corp Starbase

Planets owned by corp members carry the corp's tag, and every member gets real utility from them: land and park behind the planet's defenses, deposit to and withdraw from planet storage, and collect production. See [Planets](/guide/planets/) for how planets work in general.

A **corp Starbase** is simply a corp-owned planet with a Starbase built on it. It is the corp's shared infrastructure:

- The **ship pool** (above) operates only here.
- Heads up: because fleet loot lands in plain planet storage, **any member can withdraw it**. Treasury discipline is a social contract, not a game rule.

A corp Starbase is where the ship pool lives and where members can stage shared assets.

## Friendly Fire: What Protection Actually Covers

Corp membership blocks **direct combat** between members: 1v1 PvP attacks and fleet attacks against a corp-mate are refused outright.

That is the whole shield. It does **not** extend to indirect harm:

- Corp-mates **trigger each other's mines** and **sector defenses**, and take full damage from them.
- Corp-mates **can siege and capture each other's planets**.

Coordinate deployments with your corp. Tell people where your mines are, and don't garrison a sector your corp-mates route through. One protection does run in your favor: a ship parked on a corp planet cannot be attacked until the planet itself falls.

## A Warning for Founders

**Leadership cannot be handed off.** There is no way to promote another member to Leader, and a Leader cannot leave the corp while other members remain. Your only exit as a founder is to kick every member and dissolve the corp — which destroys the corp bank with it.

Choose to found a corp knowing you'll captain it for the season. If you just want to fly with a crew, join someone else's corp instead.

Leaving as a Member or Officer is clean at any time. When the last member (the Leader) leaves, the corp dissolves and its bank balance is gone.

## Fleets

Fleets are corp-exclusive group combat: up to **3 ships, including the leader**, attack one player target as a single combined force.

### Forming a Fleet

Open the **Battle Station** — Nav tab → the players-in-sector list → **Engage** — and use the Corp Fleet section to form a fleet or join one. Requirements:

- Same corporation as the fleet.
- Same sector as the fleet.
- Not cloaked.

Forming and joining are free — no credits, no turns. The player who forms the fleet is the fleet leader.

### Fleet Attacks

Only the **fleet leader** initiates a fleet attack, and it costs **1 turn — paid by the leader only**. Standard PvP rules apply to the target: no corp-mates, no Federation space, PvP must be enabled in the galaxy, and the target can't be docked, disabled, protected, or immune. See [Combat](/guide/combat/) for the underlying resolution rules.

The fleet fights as one ship: the pooled fighters, shields, and torpedoes of every participating member, built on the leader's hull. One combined attack roll decides the whole fight — no per-member retreats. Members who are out of the sector, cloaked, docked, or disabled when the attack fires silently sit out. Everyone who participates has their cloak broken.

Win or lose, combat losses are split across members in proportion to what each contributed. If the fleet **loses**, every participant's ship is disabled (with the standard 2-minute PvP immunity), a participant who entered with zero shields, fighters, and torpedoes is destroyed — and the target loots credits **from the leader**. Leading a fleet means holding the bag.

### Fleet Loot

Fleet loot does not go to individuals: **looted credits go to the corp bank**. As with all PvP, loot is credits only — the target's cargo is not transferred.

Individual members still earn XP, reputation, and PvP win stats; the leader gets the kill credit.

### Leaving and Disbanding

Any member can leave a fleet at any time. If the leader leaves — or the last member does — the fleet disbands. Note that flying out of the sector does not formally remove you from the fleet roster; you simply won't participate in any attack fired while you're away.

## Corp Leaderboard

Corps compete as a category on the season leaderboards (Feed tab). A corp's score sums its members' missions, XP, and credits earned — so every member's grind counts.
