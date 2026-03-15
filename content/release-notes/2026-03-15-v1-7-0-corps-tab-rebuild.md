---
title: "v1.7.0 — Corps Tab Rebuild"
date: 2026-03-15T19:20:00-04:00
type: blog
description: "v1.7.0 rebuilds the Corps tab with inline cards, fixes corp browse reliability, and cleans up corporation actions throughout the UI."
---

v1.7.0 is a bigger corporation update that rolls the recent corps fixes into a cleaner, more integrated interface.

The Corps tab has been rebuilt from the old sub-tab layout into a card-based screen that stays in theme with the rest of the app and puts the most important actions directly in front of you.

## Corps Tab Rebuild

The old My Corp / Browse / Create sub-tabs are gone.

If you are not in a corporation, the Corps tab now shows:

- a **Browse Corporations** card with a compact table view
- a **Create Corporation** card with an inline creation form

If you are already in a corporation, the Corps tab now shows inline cards for:

- corporation info
- members
- banking
- management
- recent activity

This replaces the old modal-heavy flow with a layout that is faster to use and visually consistent with the app's teal-on-dark theme.

## Browse and Join Improvements

The browse experience is more useful now:

- corps show in a simple table layout
- open vs closed status is visible at a glance
- member counts are visible in-line
- joining an open corporation is now a direct action from the list

This release also includes the underlying browse-list fix from v1.6.2, which removed a missing Firestore composite-index dependency that could cause the browse tab to appear empty.

## Management and Banking Inline

Corporation banking is now handled inline instead of in a separate modal. Deposit and withdraw flows are part of the main Corps screen.

Management actions are also more direct. Leaders and officers can manage members from the same screen, and leaders can update policies inline without leaving the page.

## Data and Reliability Updates

A few backend and data-shape improvements are included as part of this release:

- corp list responses now include join policy data
- browse queries avoid the missing-index failure path
- document ID handling is safer
- public bank balance handling is null-safe

Overall, v1.7.0 makes corporations easier to browse, join, manage, and understand.
