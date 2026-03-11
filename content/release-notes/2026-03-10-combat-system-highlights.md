---
title: "Combat System Highlights: v1.2.6 through v1.4.3"
date: 2026-03-10T21:00:00
type: blog
description: "A look back at everything that changed with combat, ship repair, and weapons from v1.2.6 through v1.4.3 — shields, fighters, torpedoes, and what it actually means to lose a fight."
---

Over the past couple of weeks, combat has seen the most significant overhaul in Big Bang Smugglers history. This is a quick summary of what changed and why.

## Shields Are Now the Only Thing You Repair

Before v1.4.0, repair was a blurry concept. The starport would try to restore fighters, torpedoes, and shields all at once, but the math was inconsistent and the display was confusing. More importantly, it didn't make a lot of thematic sense — you don't "repair" bullets.

Starting with v1.4.0, **shields are the only thing you repair**. They represent your ship's actual structural defense, and they can be patched up at any starport or port. The repair cost scales with how much damage you've taken.

Fighters and torpedoes are now **consumables**. You spend them in battle and buy more when you need them.

## Fighters and Torpedoes Are Attack, Shields Are Defense

Combat power used to be a single blended number. Now it's split:

- **Shields** contribute to defense only — they make you harder to damage and harder to disable
- **Fighters** are pure attack — light, cheap, and they add up in numbers
- **Torpedoes** are heavy attack — each one hits harder than two fighters, but costs more

This gives ship loadout some actual meaning. A ship stacked with fighters hits hard but drops quickly. A ship heavy on shields can take a beating but won't do much damage. Most players will want a mix depending on what they're flying.

## Buying Weapons in Bulk

Early versions made you buy fighters and torpedoes one at a time from the shipyard. That's gone. The Fighter Bay and Torpedo Bay now let you set a quantity and buy everything at once — 75 credits per fighter, 150 per torpedo, up to your ship's maximum.

## Losing a Fight Actually Means Something Now

This is the one that took a few passes to get right.

For a while, losing a battle looked correct on screen — the recap showed your damage, the NPC looting your credits and cargo, your ship getting disabled — but when you closed the modal, nothing had actually changed. Your credits were the same. Your fighters were fine. Your ship was still flying.

The root cause turned out to be a database transaction ordering bug. Combat effects were being written to Firestore in a sequence that caused the transaction to fail silently. The recap data came from the pre-computed result, so it always looked right. The actual writes just never happened.

As of v1.4.3, losing a fight has real consequences: your shields and fighters take damage, credits and cargo get looted proportional to what you were carrying, and if your shields hit zero your ship is disabled until you make it to a starport. Ships disabled in combat also have a short grace period before the auto-repair system can restore them, so a rough fight can't be immediately undone by a turn reset.

## What's Next

Combat is in a solid place now. The next focus areas are the mission system, port economics, and long-term progression rewards. More on those soon.
