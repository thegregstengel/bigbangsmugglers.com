---
title: "Smuggling & Contraband"
date: 2026-07-02
draft: false
description: "Run contraband, handle Federation customs and patrols, and use the black market"
weight: 10
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

Smuggling is a margin game. Contraband is bought at a steep black-market discount and sold at full commodity prices — the discount *is* the profit. The risk is real but specific: two separate detection checks, both of which you can plan around.

## What Is Contraband?

Contraband is cargo purchased through the **Black Market** port service. Ordinary commodities bought at Black Market ports carry the same flag (silently, at full price), and so do goods stolen in trading-post robberies. Contraband lots are permanently flagged in your cargo hold and sell as the underlying commodity they mimic.

| Item | Buy Price | Cargo Weight | Max per Purchase | Sells As |
|------|-------|--------------|------------------|----------|
| Stolen Equipment | 40 cr/unit | 2 holds/unit | 50 | Equipment |
| Embargoed Organics | 30 cr/unit | 1 hold/unit | 80 | Organics |
| Black Tech | 150 cr/unit | 2 holds/unit | 10 | Equipment |

Black-market purchases **cost no turns**, and supply is unlimited — the only limit is the per-purchase cap, so you can buy repeatedly until your holds or wallet run out.

## Where to Buy Contraband

Contraband is sold at the Black Market service of Pirate Bases (found in pirate and unincorporated space) and Black Market ports (pirate space only). Navigate to the sector, open the port from the Nav screen, select **Black Market** from the port services, and purchase what you need.

## Sell Values and Margins

Contraband sells as its underlying commodity at that port's normal prices — there is no special contraband price. That means the best outlet for each item is whichever port type pays the most for its commodity:

- **Stolen Equipment** is the standout. Agricultural ports pay the galaxy's top equipment prices — roughly **570 cr/unit net profit** on a 40 cr buy.
- **Embargoed Organics** sell best at mining ports, for roughly **145 cr/unit net**.
- **Black Tech** sells as equipment too, so it fetches the same price as Stolen Equipment everywhere — about **460 cr/unit net** after its much higher cost, and it's capped at 10 units per purchase. Credit for credit, Stolen Equipment is the better buy.

**Route advice: buy at pirate-space black markets, sell at neutral high-band ports.** Never sell at Federation ports — they're the only ports that run customs scans, *and* they pay less for equipment than agricultural ports do. There is no reason to bring contraband to a Federation dock.

## Detection: Two Separate Checks

### 1. Federation Customs (Entry Scans)

Customs fires when you **open the trade screen at a Federation-type port**. A 30-minute cooldown prevents back-to-back customs scans.

Detection odds:

| Your Gear | Chance of Being Caught |
|---|---|
| Nothing | 75% |
| Stealth Hull Plating only | 45% |
| Goods Cloaking Device only | 25% |
| Both | 5% |

A Goods Cloaking Device is **consumed every time a scan fires — caught or not**. One device per scan.

If you're caught: **all your contraband is seized — everywhere in the galaxy, including lots stored on your other ships** — plus a fine of 10% of the contraband's purchase value and **−5 alignment**.

**Patrol encounters** can also demand a scan. When you run into a Federation patrol while moving, you get choices: submit to the scan (a clean scan earns you **+2 alignment**), pay a bribe (500 to 25,000 cr depending on the patrol's tier, 60% success, better odds for pirate-aligned captains — a failed bribe costs the credits, dings your alignment, and forces the scan anyway, with an extra 2,000 cr fine if it catches you), **jettison your contraband first (free, no penalty** — but it dumps all contraband you own, galaxy-wide), or fight.

### 2. Point-of-Sale Checks

Separately, every time you sell a contraband lot, the port may flag the sale. The chance varies by region — from about **1%** out in the rim to about **22%** in the Federation core — and rises with criminal alignment and a fuller cargo hold.

- **Stealth Hull Plating helps here** (and usually zeroes the roll outside the Federation core).
- **The Goods Cloaking Device does NOT** — it only affects entry scans.

A flagged sale is simply **refused**: no fine, no seizure. The goods stay in your hold.

## Counter-Detection Gear

**Goods Cloaking Device** — the smuggler's staple.

- Price: 750 cr each
- Where to buy: Black Market, in the Counter-Detection Tools section (max 10 per purchase)
- Effect: drops entry-scan detection from 75% to 25%
- Usage: single-use, consumed automatically when an entry scan fires, whether you're caught or not. Does nothing at point of sale.

Your current device count is shown in the black market UI. Devices stay in your inventory between sessions (within a season).

**Stealth Hull Plating** — the permanent upgrade.

- Price: 20,000 cr plus a 5,000 XP requirement, from the Tech Hub Upgrades service
- Effect: −30 points on **both** checks — entry scans (75% → 45%, or 25% → 5% with a device) and point-of-sale rolls

## The Standing Angle

Your alignment changes the smuggling math more than any gadget:

- **Alignment above +300 makes you immune to customs entirely.** Federation entry scans — port customs and patrol searches — skip you completely, and your cloaking devices are never consumed. Ironically, a captain in good Federation standing is the galaxy's most untouchable smuggler.
- **Contraband can never be looted from you in combat.** Win or lose, PvP or NPC, contraband lots are ignored by looting — it's the safest cargo you can carry into a fight.
- Put together: a clean-standing hauler running pirate goods through neutral space faces almost no risk at all.

Getting caught pushes the other way: each bust is −5 alignment, and repeated busts drift you toward Pirate standing — which opens pirate-faction benefits but eventually closes Federation starports.

## Cargo Mechanics

Contraband lots are flagged in red on your Ship screen's cargo card and marked **"sells first"** — when you sell a commodity, the sell dialog automatically allocates contraband lots before your legitimate stock.

Remember that seizures and jettisons apply to **all contraband you own in the galaxy**, not just what's on your active ship. Stashing contraband on a hangared ship does not protect it.

## Smuggling Strategy

**The standard run:** buy Stolen Equipment at a black market, haul it to a neutral agricultural port, sell. No Federation port ever touches the route, so the only risks are patrol encounters on the way — where jettisoning is always a free out — and the point-of-sale roll, which is small in neutral space and smaller with plating.

**The bulk-organics variant:** Embargoed Organics are half the profit per unit but only 1 hold each and an 80-unit purchase cap — better for small ships and quick loops between a black market and a nearby mining port.

**The lawful smuggler:** build alignment above +300 (patrol scans while clean, Federation missions, hunting pirates) and customs stops existing for you. Combine with plating and neutral-space selling, and smuggling becomes nearly risk-free income.
