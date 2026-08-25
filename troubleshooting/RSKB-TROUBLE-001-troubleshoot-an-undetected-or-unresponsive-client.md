---
id: RSKB-TROUBLE-001
title: Troubleshoot an undetected or unresponsive client
product: raysync
components:
- user-portal
- desktop-client
domain: troubleshooting
access_level: public
audience:
- end-user
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Why does the portal say that the Raysync client is not detected?
- What should I record when the browser plug-in will not reconnect?
- Can basic web transfer continue while the desktop client is unavailable?
keywords:
- client not detected
- browser plug-in
- web transfer
- raysync-watch
- Why does the user portal say the Raysync client is not detected?
- client not started
- Start button
- desktop client
legacy_ids:
- FAQ-TROUBLE-001
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-001 | Why does the user portal say the Raysync client is not detected?
  evidence_type: generated-faq
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-002 | Why does the Raysync client still fail after a normal start attempt?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-003 | What changed for end users in Raysync 8.1.8.1?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-027 | Support file transfer with http web (support drag file and pause, cancel a task)
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Troubleshoot an undetected or unresponsive client

## Short answer

The portal has not connected to the browser plug-in client. Without an active client, Raysync can switch to web TCP mode, which supports normal upload, normal download, invite upload, and share download, but client-dependent features are unavailable.

## Likely cause

The user portal cannot detect an active browser plug-in connection. Raysync documents an automatic switch to web TCP mode when the browser plug-in is not activated. This is a detection state, not by itself a diagnosis of installation or startup failure.

## What the user can check

Confirm whether the automatic web TCP fallback appears and whether normal upload, normal download, invite upload, or share download remains available. Record the exact detection message, browser and operating system, whether the client icon appears, and whether the state changes after the normal client-start attempt described in the user guide. Detailed failure after that attempt belongs in FAQ-TROUBLE-002.

## When to contact an administrator

Contact the administrator if detection does not recover after the normal start attempt, or if the portal neither detects the client nor provides the documented web fallback. Provide the recorded message, browser, operating system, client version if known, and whether web TCP transfer works.

## Version differences

Current documentation permits pause or cancel controls for some web transfer tasks without the client, but not universal client-free feature parity. The release FAQ associates that capability with 8.1.8.1, while the feature matrix associates it with 6.3.8.0. These are competing historical claims, so the introduction point is unresolved and no introduction version is selected.

## Important notes

Use only the client package and portal address approved by your organization.

## Related documented boundaries

- **Why does the Raysync client still fail after a normal start attempt?:** This condition applies after you already used the normal **Transfer List > Start** attempt. If the browser plug-in or desktop client still does not run or reconnect, record what happened and collect client evidence rather than repeating the complete installation or launch procedure.
