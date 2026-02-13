---
title: "Federation Starports: A Complete Redesign"
date: 2026-02-12
draft: false
description: "We've completely redesigned Federation Starports from a tab-based menu into an immersive directory of distinct businesses and services."
tags: ["features", "ui", "starports"]
---

Today we're excited to share a major redesign of Federation Starports - one of the most significant UI improvements in Big Bang Smugglers to date.

## The Problem with the Old Design

Previously, starports were presented as a simple tab interface: "Services" and "Warp Drive". While functional, this felt more like a flat menu system than a physical location in the game world. It didn't capture the sense of walking into a bustling space station with different businesses and offices.

## The New Approach: Starports as Physical Locations

We've completely reimagined starports as **physical locations** with distinct places you can visit. When you dock at a Federation Starport, you now see a directory screen welcoming you to the station:

**"Welcome to the Federation's Starport"**

Below that, you'll find six distinct locations, each with its own branding and specialized services:

### 🏦 Federation Reserve Bank
Your first stop for financial security. The Federation Reserve Bank offers:
- Secure credit storage separate from your ship's wallet
- Zero-fee deposits and withdrawals
- Protection from loss if your ship is destroyed

**Status**: ✅ Fully implemented

### 🔧 TriStar Shipyard & Maintenance Bay
A full-service ship maintenance and modification hub. TriStar offers:
- Ship renaming (1,000 credit fee)
- Professional shipyard-grade repairs (full restoration when disabled)
- Warp drive installation and upgrades
- Weapons systems (coming soon)
- Cargo hold modifications (coming soon)

**Status**: ✅ Rename & Repair implemented

### 🚀 Nebula Ship Sales & Acquisitions
Your trusted ship dealer with automatic trade-in services:
- Browse available ship classes
- Compare specs: hull, shields, cargo, speed
- Purchase with automatic trade-in of your current ship
- No multi-ship ownership (one ship per captain)

**Status**: ⏳ Coming soon

### 📋 Federation Contract Office
Official Federation missions and bounty postings:
- Accept faction missions for credits and reputation
- Take bounty contracts on hostile NPCs
- Track active contracts and rewards

**Status**: ⏳ Coming soon

### 👥 Vanguard Colonial Recruitment
Hire trained personnel for planetary operations:
- Security personnel (fighters) for planetary defense - 500 cr/unit
- Mining workers for resource extraction - 300 cr/unit

**Status**: ⏳ Coming soon

### 📦 CoreStar Tactical Supply
Authorized dealers in defensive technology:
- Navigation beacons for sector marking - 2,500 cr
- Proximity mines for sector defense - 5,000 cr
- More tactical equipment coming

**Status**: ⏳ Coming soon

## Why This Matters

This redesign achieves several goals:

**1. Immersion**: Each location feels like a real business with its own name and focus, not just a menu item.

**2. Organization**: Services are logically grouped by type - banking is separate from ship services, which is separate from personnel hiring.

**3. Scalability**: Each location can grow independently. Adding new ship services doesn't clutter the banking interface.

**4. Future Expansion**: We can easily add more locations (cantinas for intel, black markets for contraband, etc.) without redesigning the entire system.

## Implementation Details

For the technically curious:

- Each location opens in a full-screen modal with proper safe area handling (no more content hidden under phone notches!)
- All modals share consistent header/footer patterns
- Form inputs use native React Native components with proper validation
- Backend integration uses existing cloud functions where available
- Each feature is tracked as a separate GitHub issue for clear progress

## What's Working Now

As of today, you can:

✅ **Bank your credits** - Deposit and withdraw with real-time balance updates  
✅ **Rename your ship** - Give your vessel a proper name (3-30 characters, profanity-filtered)  
✅ **Repair your ship** - Full shipyard-grade restoration when disabled  

## What's Next

We have 12 GitHub issues tracking the remaining features across all six locations. Here's the immediate roadmap:

**Next Up:**
- Warp drive installation and upgrades in TriStar Shipyard
- Ship browsing and purchase in Nebula Ship Sales
- Mission and bounty display in Contract Office

**Coming Soon:**
- Personnel hiring in Vanguard Recruitment
- Tactical equipment purchases in CoreStar Supply
- Weapons and cargo upgrades in TriStar Shipyard

## Try It Yourself

If you're in the alpha test group, update your app and head to any Federation Starport. The new directory interface will greet you immediately.

We're excited about this change and believe it sets the foundation for a much more immersive starport experience. More updates coming soon!

---

*Have feedback on the new starport design? Let us know!*
