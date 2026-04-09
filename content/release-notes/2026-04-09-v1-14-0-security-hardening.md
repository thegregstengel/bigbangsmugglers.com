---
title: "v1.14.0 — Security Hardening and Web Launch Prep"
date: 2026-04-09T17:30:00-04:00
type: blog
description: "v1.14.0 strengthens account and session security across all platforms, adds clickable links to notifications, fixes cargo hold upgrade costs in starport shipyards, and prepares the app for browser-based play."
---

v1.14.0 is a security-focused release that hardens account protection, improves session safety, and lays the groundwork for the upcoming web launch.

## Stronger Account and Session Security

This release adds multiple layers of protection to how the game verifies your identity and safeguards your session.

Client connections now use device-level attestation, session storage is more resistant to common browser-based attacks, and server-side checks are stricter about who can access what. These changes apply across Android, iOS, and the upcoming web client.

## Tighter Data Boundaries

Game data access is now more precisely scoped so players can only see information relevant to their own ships, planets, and galaxies.

This doesn't change gameplay, but it means the backend is better at enforcing the rules that were always intended — no peeking at someone else's bank balance.

## Notification Links

In-game notifications can now include tappable links. When we send update notices or event announcements, you'll be able to tap through directly to the relevant page or store listing.

## Starport Shipyard Fix

The five-tier cargo hold upgrade display now appears correctly in starport shipyards. Previously, the tiered milestone UI only showed on the ship services screen — starport shipyards still showed the old single-purchase button and could calculate wildly incorrect prices.

## Season Ending Improvements

Season endings can now be triggered immediately when needed, instead of requiring a minimum one-day countdown. This gives us more flexibility to wrap up seasons cleanly during events or maintenance windows.
