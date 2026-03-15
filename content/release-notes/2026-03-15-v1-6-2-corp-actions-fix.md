---
title: "v1.6.2 — Corp Actions and Browse Fixes"
date: 2026-03-15T11:45:00-04:00
type: blog
description: "v1.6.2 fixes corporation actions showing false errors and restores the corp browse list by removing a missing-index query path."
---

v1.6.2 is a corporation hotfix.

It fixes two separate issues in the corporation screens: actions that could report false errors even when they succeeded, and a Corp Browse query that could silently return an empty list.

## Corp Actions Fix

Several corporation flows were checking the wrong response fields in the app. The backend action could succeed, but the UI would still show an error message.

This update fixes false error states for:

- corporation member management
- corporation policy updates
- corporation creation
- corporation banking actions

## Corp Browse List Fix

The Corp Browse tab could appear empty even when corporations already existed in the current galaxy.

The root cause was a Firestore query path that combined a galaxy filter with sorting by member count, which required a composite index that had not been created. When that query failed, the error was caught and the UI ended up showing an empty list.

v1.6.2 removes that index dependency from the browse query, then sorts and paginates the results in memory instead. The fix also tightens up document ID usage and adds null safety for public bank balance data.

As a result:

- existing corps should now appear correctly on the Corp Browse tab
- alignment filtering should continue to work
- search by corp name or leader name should continue to work
- corps should still display sorted by member count

This release follows v1.6.1, which fixed corporation alignment button layout on the browse and create screens.
