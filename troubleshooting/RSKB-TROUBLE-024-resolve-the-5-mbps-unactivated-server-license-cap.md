---
id: RSKB-TROUBLE-024
title: Resolve the 5 Mbps unactivated-server license cap
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
- Why is every transfer capped near 5 Mbps on an unactivated server?
- How can I distinguish the license cap from ordinary network slowness?
- Who can activate the server when the documented speed limit applies?
keywords:
- 5 Mbps
- license
- unactivated server
- speed limit
- Why is my Raysync server transfer limited to about 5 Mbps?
- troubleshooting
- Raysync
legacy_ids:
- FAQ-TROUBLE-007
safety_tags:
- license-control
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-007 | Why is my Raysync server transfer limited to about 5 Mbps?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Resolve the 5 Mbps unactivated-server license cap

## Short answer

An unactivated Raysync server has a documented default bandwidth of 5 Mbps. License activation is required to experience the maximum speed.

## Diagnostic boundary

This exact 5 Mbps condition is the documented unactivated-server license cap. It is separate from ordinary slow-transfer diagnosis and from a port or connectivity failure.

## Likely cause

The server license has not been activated or activation has not taken effect. This is a server-wide condition, not a per-task desktop client setting.

## What the user can check

Compare the observed rate across more than one task and ask whether the deployment is activated. You can also inspect the client task speed and details, but an end user cannot activate the server.

## When to contact an administrator

Contact the administrator if transfers consistently approach the documented 5 Mbps ceiling. Ask them to verify license status. License activation and the required server restart are administrator operations.

## Version differences

The current server information guide documents the 5 Mbps default. The release list does not identify a later removal of this unactivated-server behavior.

## Important notes

Do not confuse 5 Mbps (megabits per second) with file-size units shown elsewhere. Other bandwidth limits and network conditions can also reduce speed, so the 5 Mbps observation alone does not prove license state.
