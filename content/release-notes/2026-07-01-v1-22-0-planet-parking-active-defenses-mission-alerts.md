---
title: "v1.22.0 — Planet Parking, Active Defenses, and Mission Alerts"
date: 2026-07-01T00:00:00Z
type: blog
description: "v1.22.0 lets ships land on owned planets for citadel protection, scales garrison strength by citadel level, adds mission-expiry push notifications, ships an in-app catalog with full specs, and fixes several mine and combat bugs."
---

v1.22.0 makes your planets meaningfully harder to crack, adds a full in-app ship catalog, and pushes reminders before your missions expire.

This release also closes several mine-behavior bugs and tightens up combat rules that were leaving gaps in what sector defenses actually covered.

## Planet Parking and Citadel Defense

Ships can now land on planets you own. While landed, the full citadel defense stack — shields, garrison fighters, deployed mines — applies before an attacker can reach your hull. Your planet has to fall before your ship does.

Citadel level now also scales the number of garrison fighters available for sector defense. Higher-level citadels give you substantially more defensive firepower, making the investment in planet development pay off more directly in combat.

## Sector Defenses on Entry

Sector defenses now auto-engage any intruder the moment they enter a defended sector, regardless of what action they attempt first. A rules gap existed where certain entry behaviors could occur before defenses triggered; that gap is closed.

## Mission Expiry Alerts

A background check now runs hourly and sends a push notification when any of your active missions are approaching their deadline. You get a warning window before time runs out rather than discovering a missed reward after the fact.

## In-App Ship Catalog

The full ship catalog is now available inside the app. All classes — including ships you haven't unlocked yet — show complete specs: cargo holds, fighters, shields, torpedoes, XP requirement, and tier. No need to tab out to the website to compare ships you're saving toward.

## Mine Fixes

Three mine bugs are resolved in this release.

Deploying multiple mines now places the full selected quantity. Previously, only one mine was placed regardless of how many you chose.

Mine counts update immediately after deployment instead of showing stale totals.

Entering a sector where you have deployed your own mines no longer triggers them against you.

## Shipyard Capacity Upgrades Restored

Fighter, torpedo, and shield capacity upgrade tiers are now visible and purchasable in the TriStar Shipyard alongside the existing cargo upgrades. These tiers were active in the backend but were not rendering in the Shipyard UI.

## Combat and Port Fixes

Pirate ports located in pirate space can now be attacked when port combat is otherwise available. A configuration gap was blocking attacks specifically in pirate-space sectors.

## Warp Panel Persistence

The Warp panel on the Nav screen now remembers whether you had it expanded. It stays open between jumps instead of collapsing every time.

## UI Cleanup

Ship Services screen has been retired. Tesseract is accessible from its new home. Special Orders have been removed.
