---
title: "v1.5.3 — Inventory & Ship Services Fix"
date: 2026-03-13T21:00:00
type: blog
description: "v1.5.3 fixes mining workers not showing on the planet screen and Ship Services being unusable."
---

v1.5.3 is a hotfix for two broken screens introduced in v1.5.2.

## Mining Workers Not Showing

Players with mining workers in their ship inventory were seeing "No Mining Workers in inventory" on the Planet screen despite having workers available. The fix restores the inventory data feed to the planet screen so worker counts display correctly and deployment works as expected.

## Ship Services Broken

The Ship Services screen at starports was completely unusable — tapping into it produced errors. This was caused by the same missing inventory data connection. Both screens are now fixed.
