---
title: "v1.17.2 — Season-End Stability"
date: 2026-05-08T12:00:00Z
type: blog
description: "v1.17.2 fixes a blank-screen issue after season end and corrects post-season world cleanup so old sectors, ports, and planets are properly removed."
---

v1.17.2 is a stability patch addressing two issues uncovered after the Red Dwarf beta season ended.

## Blank Screen on Season End

The app could briefly show a blank screen when launched after a season had closed, then loop back to the recap screen repeatedly. Both issues are resolved; the app now navigates correctly to the season recap on first open.

## Post-Season World Cleanup

After a season ends, sectors, ports, planets, and player galaxy links are supposed to be cleared automatically. A missing function registration meant this cleanup job was never deployed and never ran, leaving old world data in place indefinitely. The registration has been corrected; ended seasons will now be fully cleaned up and archived as intended.
