---
title: "v1.5.5 — Trading UI & Toast Fixes"
date: 2026-03-14T14:00:00
type: blog
description: "v1.5.5 fixes the trading commodity layout and makes toast notifications visible above all modals."
---

v1.5.5 is a polish update with two UI fixes.

## Trading Screen Layout

Buy and sell controls are now on separate rows instead of crammed side-by-side on one line. Each row has a label, a quantity input, a Max button, and a Buy or Sell button. This makes the trading interface much easier to use, especially on smaller screens.

## Toast Notifications Above Modals

Toast notifications were invisible when a modal was open — for example, buying a ship at a starport would show a success or error toast behind the modal instead of on top of it. Toasts now render above all modals so you always see the feedback. The ship purchase screen also now validates your XP level before letting you attempt the purchase, so you get a clear message instead of a backend error.
