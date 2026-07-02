---
title: "Ships"
date: 2026-07-02
draft: false
description: "Every ship class in Big Bang Smugglers, with stats, prices, and how buying, the Hangar, and destruction actually work"
weight: 5
toc: true
---

*Accurate as of v1.22.0 (July 2026).*

Your ship is everything. It determines how much you can carry, how hard you hit, and whether you make it home. Ships come in six roles, five tiers each, split cleanly between Federation and Pirate lines. Which line you can buy from is decided by where you are standing: Federation starports stock Federation hulls, pirate havens stock Pirate hulls, and your alignment decides which of those doors will open for you in the first place.

## How Ships Work

Every ship has four core stats:

- **Cargo Holds** — how many units of fuel, organics, or equipment you can carry
- **Shields** — your first line of defense in combat
- **Fighters** — escort craft that engage in battle
- **Torpedoes** — offensive weapons for striking enemies

Tier determines the base power level and the price. XP gates and hull prices are uniform across every role and both factions:

| Tier | XP Required | Hull Price |
|------|-------------|------------|
| 1 | None | 5,000 cr |
| 2 | 2,000 XP | 15,000 cr |
| 3 | 8,000 XP | 40,000 cr |
| 4 | 25,000 XP | 100,000 cr |
| 5 | 60,000 XP | 250,000 cr |

Those are base prices — what you actually pay varies with your standing at the starport selling the hull. The purchase screen shows the pricing breakdown before you commit.

## Role Identities

Each of the six roles has a distinct stat identity. Two things the rumors get wrong, corrected here:

- **Shields are identical across all roles at each tier** — 150 / 225 / 350 / 525 / 800 for Tiers 1 through 5. Nobody out-tanks anybody at the same tier.
- **Every Pirate hull is an exact stat mirror of its Federation counterpart** — same holds, shields, fighters, torpedoes, and price — except the escape rating, which is 10 points better on every Pirate ship. That is the actual faction trade-off.

| Role | Faction | Cargo | Fighters / Torpedoes | Escape | Primary Use |
|------|---------|-------|----------------------|--------|-------------|
| Trading | Federation | Highest | Lowest | 30% | Commodity hauling |
| Smuggling | Pirate | Highest | Lowest | 40% | Contraband hauling |
| War | Federation | Minimal | Highest | 40% (30% at Tier 5) | Combat and PvP |
| Raider | Pirate | Minimal | Highest | 50% (40% at Tier 5) | Pirate combat |
| Balanced | Federation | Medium | Medium | 50% | General purpose |
| Corsair | Pirate | Medium | Medium | 60% | Pirate general purpose |

**Trading vs. Smuggling:** Both carry the most cargo of any role. Smugglers get the standard Pirate 10-point escape edge, which matters more when what you are hauling invites questions.

**War vs. Raider:** Glass cannons — maximum fighters and torpedoes, minimal cargo. Note that the Tier 5 flagships in both lines trade 10 points of escape for their damage bonus.

**Balanced vs. Corsair:** These are the escape artists, not the tanks. Their identity is the best escape rating in their faction plus middle-of-the-road cargo and firepower. The Corsair line's 60% is the best escape rating in the game.

In combat, your final retreat chance (after ship ability bonuses) is clamped between 10% and 90% — nothing is ever a guaranteed getaway, and nothing is ever completely cornered.

## Buying Ships

Ships are sold at the starport **Ship Sales** place — Nebula Ship Sales & Acquisitions at Federation starports, Prize Vessels & Salvage at pirate havens. You must be in the starport's sector, meet the XP gate, and pay from wallet credits (the bank doesn't count).

When you buy:

- Your old ship is **kept, not traded in** — it moves to your Hangar, and you can switch back or sell it later.
- Your cargo transfers to the new hull automatically. If the new ship is smaller, each commodity is trimmed proportionally and the overflow is **lost** — check your holds before downsizing.
- The new ship starts at base stats with zero upgrades. Nothing installed on the old hull comes with you.

**Stock is finite.** Each starport opens the season with a limited allocation per tier — heavier at the low end, down to one or two hulls at Tiers 4 and 5 — and sold hulls are not replaced. If someone else bought the last Federation Galleon, there isn't another one at that starport this season. Don't bank a late-game plan on a specific hull being available when you finally qualify for it.

### The Ship Catalog

The Ship Sales floor lists only what's in stock locally, but the **View Full Ship Catalog** button opens a browser with all 30 classes — full specs including base and max values per stat, escape rating, price, and XP requirement — even for ships you can't buy yet and ships that aren't stocked here. Use it to plan your progression before you've earned it.

## The Hangar

The Hangar (formerly called the Garage) holds every ship you own that isn't currently active. It is a place at every starport, and it also appears in the Starbase section of planets where you or your corporation have built a Starbase.

- **No ownership cap.** Own as many ships as you can afford.
- **Switching is free**, but only at a storage point: a starport sector, or a planet with a Starbase owned by you or your corp. Your incoming hull materializes wherever you are — ships don't have to be fetched from where you left them.
- **Valuation:** each stored hull shows "Paid X · Value Y", where the value is a flat 64% of the original purchase price. No depreciation, no condition modifier.
- **Selling** pays that flat 64%, at starports only — the Starbase hangar is switch-only. You can never sell your active ship or your last ship. Any cargo still aboard a sold hull is gone with it.

Ships are per-galaxy: your hangar doesn't follow you across galaxies, and a season reset starts you fresh with a new starter.

## Ship Destruction and Escape Pods

Losing a fight normally leaves your ship **disabled**, not destroyed. Destruction only happens when both of these are true:

1. Your shields, fighters, AND torpedoes were all at **zero when the combat started**, and
2. You lose that fight.

The game warns you when you're in that state — a "defenses depleted" banner appears on the Ship and Nav screens. If you see it, one more lost fight ends the ship. Repair or restock before anything else.

When a ship is destroyed:

- The hull is gone permanently, along with **everything installed on it** — tech upgrades, warp drive, StarNav, Tesseract, all of it.
- All cargo aboard is lost.
- **All of your remaining turns are wiped.** Your day is over.
- Destruction itself takes no credits or XP — but the fight you just lost still applies normal combat looting to your wallet before the ship goes down. Bank credits stay safe.

Your escape pod takes you to the sector of a planet where you own a built Starbase — or to Sector 0 if you don't have one. If you have surviving ships in the Hangar, the first one is reactivated there. If you own nothing else, you're granted a free starter ship.

See [Combat](/guide/combat/) for how fights are resolved and how to avoid getting stripped in the first place.

## Renaming Your Ship

Any ship you own can be renamed for a flat **1,000 credits** at the starport Shipyard. A small luxury, but yours.

## A Note on the Starter Ship

The free starter — granted at season start or after losing everything — is an "SS Starter": a stripped-down Frontier Scout hull with 20 holds, 15 shields, no fighters, no torpedoes, and a 30% escape rating. That is far below what the class is capable of. A real catalog **Frontier Scout at 5,000 credits** (40 holds, 150 shields, 23 fighters, 12 torpedoes, 50% escape) is one of the biggest single upgrades you will ever buy per credit spent. Make it an early priority.

---

## Federation Ships

Federation vessels are built by licensed shipyards and run clean. They favor cargo capacity and by-the-book engineering over raw aggression.

### Trading Line

Traders haul more cargo than any other class. If your goal is buying low and selling high, this is your line. Escape rating: 30% across the line.

**Nebula Merchant** — Tier 1 · 5,000 cr · no XP required
The classic first real purchase. It does the job, handles decently, and nobody looks twice when it docks. Good for learning the routes before you commit to a bigger investment.

**CoreStar Freighter** — Tier 2 · 15,000 cr · 2,000 XP
A proper commercial hauler. The CoreStar line has been moving cargo across federation space for decades and the Freighter shows it. Workhorse engineering, not flashy, completely reliable.

**TriStar Hauler** — Tier 3 · 40,000 cr · 8,000 XP
Serious cargo capacity with enough shielding to survive the occasional rough sector. At this tier you stop being a runner and start being a merchant.

**Vanguard Trader** — Tier 4 · 100,000 cr · 25,000 XP
The preferred ship of experienced federation merchants. Carries enough to make large trades worthwhile and handles warp transitions cleanly.

**Federation Galleon** — Tier 5 · 250,000 cr · 60,000 XP
The largest trade vessel in federation space. Moving one of these through a sector turns heads. The cargo capacity borders on absurd, and that is entirely the point.

---

### War Line

Federation warships sacrifice cargo for firepower. Built for captains who want to fight, not haul. Escape rating: 40%, except the Battleship at 30%.

**Patrol Corvette** — Tier 1 · 5,000 cr · no XP required
Light, fast, and built to engage before the target knows what happened. Standard patrol craft for federation space. Not impressive, but more than enough for most threats.

**Strike Frigate** — Tier 2 · 15,000 cr · 2,000 XP
A step up from patrol work. The Strike Frigate is designed for sustained engagements and does the job without being particularly elegant about it.

**Battle Cruiser** — Tier 3 · 40,000 cr · 8,000 XP
This is where the war line starts feeling like a real warship. Heavy fighter complement and enough torpedo racks to make most captains reconsider a fight.

**Enforcer Dreadnought** — Tier 4 · 100,000 cr · 25,000 XP
Federation heavy enforcement vessel. Slow to maneuver, impossible to ignore. The kind of ship that ends disputes by existing in the same sector.

**Federation Battleship** — Tier 5 · 250,000 cr · 60,000 XP
The apex of federation military shipbuilding. Capital class, full armament, and a +10% damage bonus in combat — paid for with trading-freighter escape odds. Very little cargo space, very few things that can stop it.

---

### Balanced Line

Balanced ships split the difference. Reasonable cargo, reasonable combat, and the best escape rating in the Federation fleet at 50%.

**Frontier Scout** — Tier 1 · 5,000 cr · no XP required
The choice for captains who are not sure what they want yet. Decent cargo, decent shields, enough fighters to handle a scrape. A good ship to figure out your playstyle.

**Pathfinder** — Tier 2 · 15,000 cr · 2,000 XP
Multi-role and honest about it. The Pathfinder is the reliable middle option at every tier — not the best at anything, never embarrassing at anything.

**Vanguard Ranger** — Tier 3 · 40,000 cr · 8,000 XP
A versatile cruiser that has earned a reputation for surviving situations it probably should not have. Popular with captains who take their routes through mixed territory.

**Horizon Cruiser** — Tier 4 · 100,000 cr · 25,000 XP
Built for deep space work where resupply is rare and threats are unpredictable. Carries enough cargo to be profitable and enough firepower to be taken seriously.

**Federation Odyssey** — Tier 5 · 250,000 cr · 60,000 XP
Federation flagship configuration, with a +5% bonus to all activities. Built for long-range operations in uncharted space. A ship you can spend a whole season in without wishing you had brought something different.

---

## Pirate Ships

Pirate vessels come from salvage yards, black markets, and shipbreakers who ask no questions. Stat for stat they match their federation counterparts exactly — same holds, same shields, same armament, same price. What the pirate yards sell you is the extra 10 points of escape rating on every hull, which is worth more than it sounds when the math stops working in your favor.

### Smuggling Line

Smuggling ships mirror the trading line in cargo capacity with a better escape rating (40%). What they carry is often the question, not how much.

**Shadow Runner** — Tier 1 · 5,000 cr · no XP required
Built light and with as few transponder signatures as possible. Does not look like much, which is the whole idea.

**Black Market Hauler** — Tier 2 · 15,000 cr · 2,000 XP
Mid-sized and purpose-built for moving things that should not be moving. Reinforced holds, minimal external markings, and a cargo door that opens faster than most.

**Plunder Barge** — Tier 3 · 40,000 cr · 8,000 XP
Large capacity, ugly as a docking collision, and utterly indifferent to what you think about either of those things. It carries a lot and it gets there.

**Marauder's Fortune** — Tier 4 · 100,000 cr · 25,000 XP
An elite smuggling platform with a reputation that precedes it. Captains who run a Marauder's Fortune have usually been doing this long enough to know things most people do not.

**Pirate Leviathan** — Tier 5 · 250,000 cr · 60,000 XP
Maximum cargo in a hull that looks like it has survived things it should not have, plus a +15% cargo bonus from raids. The Leviathan hauls more in one run than most federation freighters manage in three.

---

### Raider Line

Raiders are built to attack and withdraw. Light on cargo, heavy on fighters and torpedoes, with a 50% escape rating (40% on the Juggernaut) to break contact when things go sideways.

**Cutthroat** — Tier 1 · 5,000 cr · no XP required
Fast and direct. The Cutthroat does not have a lot going for it beyond speed and aggression, which turns out to be enough for a surprising number of situations.

**Reaver** — Tier 2 · 15,000 cr · 2,000 XP
A boarding specialist. More organized than the Cutthroat and better suited for extended engagements where the first pass does not finish things.

**Warlord** — Tier 3 · 40,000 cr · 8,000 XP
Heavy raider with enough fighters to overwhelm most standard targets and enough hull to absorb return fire while doing it.

**Blood Talon** — Tier 4 · 100,000 cr · 25,000 XP
Apex predator configuration. The Blood Talon does not win by being fast or clever. It wins by having more fighters than the other ship can handle.

**Pirate Juggernaut** — Tier 5 · 250,000 cr · 60,000 XP
Dreadnought class from the pirate yards, with a +10% damage bonus in raids. Slower to escape than anything else in the raider line but capable of absorbing and delivering punishment that ends conversations decisively.

---

### Corsair Line

Corsairs combine decent cargo with the best escape ratings in the game — 60% across the entire line. The preferred choice for pirates who want to stay alive and profitable at the same time.

**Rogue's Gambit** — Tier 1 · 5,000 cr · no XP required
The escape artist entry point. Not the most capable ship in any particular stat, but it will get you out of a bad situation faster than almost anything else at this tier.

**Freebooter** — Tier 2 · 15,000 cr · 2,000 XP
High-agility frame built for captains who plan to operate in contested space and need to disengage cleanly when the math stops working in their favor.

**Blackheart** — Tier 3 · 40,000 cr · 8,000 XP
The corsair line flagship for most mid-game pirates. Named for the shipyard that built the first one, which has been building them ever since. Reliable, respected, and feared in the right sectors.

**Crimson Eclipse** — Tier 4 · 100,000 cr · 25,000 XP
Shadow fleet configuration. Fast, capable, and carries enough cargo to make every successful run worthwhile. The preferred ship of pirate captains who have been around long enough to have opinions about ships.

**Pirate Dominion** — Tier 5 · 250,000 cr · 60,000 XP
Corsair capital class, with a +5% bonus to all activities. Carries a full fighter complement, meaningful cargo capacity, and the highest escape rating in the game. A ship that is difficult to pin down and expensive to take on.

---

## Choosing Your Ship

The right ship depends on your playstyle more than anything else.

If you are trading, cargo holds are everything. Move to the next tier of trader as soon as your XP and credits allow — the cargo difference compounds with every run.

If you are fighting, fighters and torpedoes matter more than cargo. A well-equipped war or raider ship can hold sectors that softer vessels have to avoid.

If you are doing both, the balanced and corsair lines give you flexibility without fully committing to either extreme — and the best odds of walking away when a fight was a mistake.

If everything else is equal and you can dock at both kinds of starport, the Pirate mirror of any ship is simply the better hull: same stats, same price, 10 more points of escape.

Upgrade the ship, not the dream. A tier 3 ship you can actually afford is more useful than a tier 5 ship that empties your bank and leaves nothing for cargo — especially now that the tier 5 hull you're saving for might be sold out by the time you get there.
