---
title: "v1.17.3 — App Check Security Hardening"
date: 2026-05-20T12:00:00Z
type: blog
description: "v1.17.3 enforces App Check verification on all game API calls, adds reCAPTCHA Enterprise for web players, and fixes a mobile cold-start authentication race condition."
---

v1.17.3 is a security hardening release that rolls out App Check enforcement across the entire game backend, protecting all API calls from unauthorized access and automated abuse.

## App Check Enforcement

Every Cloud Function callable in the game now passes through an App Check verification wrapper. Requests from unverified clients are rejected, significantly reducing the attack surface for automated abuse and cheating tools. Adoption telemetry tracks enforcement rollout across the player base.

## Web Bot Protection

Web players are now verified through reCAPTCHA Enterprise, which runs invisibly in the background. This adds bot detection and abuse prevention without any player-visible friction. Content Security Policy headers have been updated to support the new verification flow.

## iOS App Attest

iOS builds now include App Attest platform tagging, providing hardware-backed device attestation for Apple devices. This is the strongest device verification available on iOS.

## Mobile Startup Reliability

A race condition could cause the first API call after app launch to fail because the App Check token had not finished minting. Tokens are now pre-minted during initialization, and all callable requests wait for token readiness before firing. This eliminates intermittent startup failures on both Android and iOS.
