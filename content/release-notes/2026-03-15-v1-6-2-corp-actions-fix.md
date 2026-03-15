---
title: "v1.6.2 — Corp Actions Fix"
date: 2026-03-15T11:45:00-04:00
type: blog
description: "v1.6.2 fixes corporation actions showing error messages even when the action actually succeeded."
---

v1.6.2 is a corporation hotfix.

Several corporation flows were checking the wrong response fields in the app. The backend action could succeed, but the UI would still show an error message.

This update fixes false error states for:

- corporation member management
- corporation policy updates
- corporation browse list loading
- corporation creation
- corporation banking actions

This release follows v1.6.1, which fixed corporation alignment button layout on the browse and create screens.
