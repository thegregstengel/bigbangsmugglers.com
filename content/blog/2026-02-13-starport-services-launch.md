---
title: "Starport Services Launch"
date: 2026-02-13
description: "12 starport features shipped in one day — the redesign is fully live with bank, shipyard, ship sales, contracts, recruitment, and tactical supply."
draft: false
sidebar:
  exclude: true
toc: false
---

Remember the [Federation Starports redesign post](/blog/federation-starports-redesign)? The one where most sections said "coming soon"?

Today we crossed them off.

12 GitHub issues closed. All six starport locations now fully operational. The redesign isn't a concept anymore — it's live.

## What Shipped

**TriStar Shipyard**

Warp drive is now a real thing you can buy and install at the shipyard. The upgrade path works too — take your existing drive and push it to the next tier. Both the install and upgrade functions went through testing and shipped today.

**Nebula Ship Sales**

You can now actually buy ships. The ship listing screen was already there from the redesign, but the purchase flow wasn't wired. Today: browse available classes, see full stats on each card, buy with automatic trade-in. One ship per captain — make it count.

**Federation Contract Office**

Mission board is live. List available missions, accept them, check the bounty board, accept bounties. The contract office was one of the most-anticipated locations given how long the mission system had been partially functional. It's wired now.

**Vanguard Recruitment**

Hire security personnel (fighters) and mining workers directly from the starport. These go to your planet garrisons — the recruitment loop now connects to the planet system.

**CoreStar Tactical Supply**

Navigation beacons and proximity mines are purchasable. Beacons had backend logic already implemented; today they got the supply chain connection. Mines same deal.

## How We Got Here

The [audit on Feb 5th](/blog/2026-02-05-auditing-the-foundation) identified what was wired and what wasn't. The [Feb 6th sprint](/blog/2026-02-06-mission-performance-docs-audit) designed the mission system that the contract office relies on. The [bug fix sprint on Feb 8th](/blog/2026-02-08-bug-fix-sprint) cleared the credits and XP field bugs that would have broken purchases.

Twelve issues in one day wasn't a rush job. It was the result of three weeks of foundation work making the final connections obvious.

Dock at any Federation Starport. Everything's open.
