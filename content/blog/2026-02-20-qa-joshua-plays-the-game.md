---
title: "QA: Joshua Plays the Game"
date: 2026-02-20
description: "The AI assistant played Big Bang Smugglers via backend CLI and found 11 bugs — trading exploits, cooldown bypasses, data crashes, and worse."
draft: false
sidebar:
  exclude: true
toc: false
---

We let Joshua (the AI assistant) play the game.

Not in a sandbox. Not against mocked data. Real game, real backend, real Cloud Functions — using a CLI tool to make API calls as a live player character. Joshua explored sectors, traded cargo, visited starports, claimed planets, and generally tried to break everything.

It worked. 11 bugs found in one session.

## What Got Found

**Galaxy generator problems**

After exploring 130+ sectors, ruins and wormhole landmarks simply weren't appearing. The galaxy generator wasn't placing them. Filed, fixed — ruins and wormhole placement now included in sector generation.

**Trading stations: completely broken**

Trading stations had no stock or price data initialized. Calling `tradeGetPortInfo` on a trading post crashed immediately on `calculateAllPrices` because there was nothing to calculate. A related issue: the trade endpoints were checking the wrong Firestore collection — `ports` instead of `stations` — so trading posts weren't accessible at all.

Two separate bugs, same broken outcome. Both fixed.

**Starport data corruption**

Three starport issues discovered by actually trying to dock:
- Starport document IDs had a double galaxy prefix (the galaxy ID was being prepended twice)
- Starport documents were missing the `tier` field entirely — returned `null`
- The galaxy generator was placing multiple ports in the same sector (sector S448 had three agricultural ports)

These were generator bugs that never surfaced in controlled testing.

**Repair exploit and balance issue**

The shipyard repair function was only available when a ship was fully disabled — you couldn't top up shields proactively. That's a design problem that forces players to let their ship get destroyed before repairing.

Separately: field kit repair on a starter ship cost 3,700 credits — 74% of the starting budget for a partial heal. Joshua flagged the balance. We scaled the cost by tier.

**Landmark cooldown exploit**

The landmark interaction handler was calling `loadNavData` — a function that doesn't exist. The success handler crashed silently, which meant landmark cooldowns were never being applied. Players could spam landmark interactions indefinitely.

**Response field mismatches**

`planetClaim` wasn't returning `cost` or `creditsRemaining`. `blackmarketBuy` used `item/totalCost` field names instead of `itemId/cost`. These weren't crashes — just broken contracts between backend and frontend.

**POI naming inconsistency**

Sector history was storing raw POI IDs instead of objects with name and type. When you looked at your explored sectors, you saw internal IDs instead of readable names.

---

Eleven issues. One session. No UI, no emulator, no manual clicking — just Joshua reading API responses and noticing when things didn't add up.

This is what real QA looks like.
