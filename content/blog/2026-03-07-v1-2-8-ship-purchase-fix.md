---
title: "v1.2.8 — Ship Purchase Fix"
date: 2026-03-07T18:00:00
description: "Version 1.2.8 fixes a bug where buying a new ship could leave your account pointing at a deleted ship, breaking ship-dependent features."
---

Version 1.2.8 fixes a data integrity bug introduced when purchasing a new ship at a starport.

## What Was Wrong

When you bought a new ship, the old ship was deleted and a new one created. The new ship was set up correctly, but your player account was not always updated to point at it. This left some players in a state where their account referenced a ship that no longer existed, which could break the ship screen, deployables, stealth scanning, and other features that depend on knowing your current ship.

## What Changed

The ship purchase transaction now atomically updates your account to reference the new ship at the same time the new ship is created. The old ship is deleted in the same operation. There is no window where your account can end up with a stale reference.

Additionally, any cargo you were carrying is now migrated to the new ship during the purchase, so nothing is lost in the transaction.

Deployable scanning, deployment, and attack functions also received fixes for a related ship lookup bug that could cause those actions to fail even when your ship was in the correct sector.
