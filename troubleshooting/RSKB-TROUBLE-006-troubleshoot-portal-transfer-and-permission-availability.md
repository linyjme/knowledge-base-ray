---
id: RSKB-TROUBLE-006
title: Troubleshoot portal transfer and permission availability
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
- Why is the upload or download action missing from the portal?
- What should I check after a file operation returns Permission denied?
- Who can resolve a forbidden path or externally owned permission?
keywords:
- permission denied
- forbidden path
- allowed path
- group permissions
- Why do I get Permission denied for a file or folder action?
- upload unavailable
- download unavailable
- web transfer
legacy_ids:
- FAQ-TROUBLE-013
safety_tags:
- authorization
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-014 | Why do I get Permission denied for a file or folder action?
  evidence_type: generated-faq
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-013 | Why is upload or download unavailable in the user portal?
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

# Troubleshoot portal transfer and permission availability

## Short answer

Availability can depend on your permission, the administrator’s transfer-type setting, and whether the client is running. Raysync can be configured for client-only transfer, web-only transfer, or both. Without the client, web TCP mode supports normal upload/download and link transfers but not every client-dependent feature.

## Likely cause

Your role lacks upload or download permission, the target path is forbidden or outside the allowed path, the server allows only the other transfer type, or the browser plug-in client is not active.

## What the user can check

Confirm the intended file area and target path. Start the browser plug-in through **Transfer List > Start** if the action is client-based. Check whether the button is missing versus an attempted task showing a specific error.

## When to contact an administrator

Contact the administrator if the button remains unavailable or permission is denied. Provide the space/group, path, action, and whether web or client transfer was attempted.

## Version differences

Current documentation permits pause or cancel controls for some web transfer tasks without the client, but not universal client-free feature parity. The release FAQ associates that capability with 8.1.8.1, while the feature matrix associates it with 6.3.8.0. These are competing historical claims, so the introduction point is unresolved and no introduction version is selected.

## Important notes

Do not use a different account to bypass permissions.

## Related documented boundaries

- **Why do I get Permission denied for a file or folder action?:** "Permission denied" usually identifies policy ownership rather than a missing file. The denied action may be excluded from your personal or group role, the path may be forbidden or outside allowed paths, or an externally authenticated account may receive permissions from Raysync or from the external authentication service.
