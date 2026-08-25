---
id: RSKB-INTEGRATION-047
title: Administer share links over the Admin API
product: raysync
components:
- admin-portal
- http-api
domain: integrations-api
access_level: support
audience:
- developer
- support-engineer
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- How does an administrator list every user's share links through the API?
- What is the difference between canceling and deleting a share link in the Admin API?
- Which Admin API path cancels a share URL list?
keywords:
- /api/share/link/list
- /api/share/link/cancel
- /api/share/link/delete
- shareUrlList
legacy_ids: []
safety_tags:
- authorization
- credentials
- destructive-operation
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-040
- RSKB-INTEGRATION-050
- RSKB-SHARE-007
source_refs:
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: ShareLinkResource
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Administer share links over the Admin API

## Short answer

Administrators list all users' share links with `GET /api/share/link/list`, cancel with `PATCH /api/share/link/cancel`, and delete with `DELETE /api/share/link/delete`. Cancel invalidates access while the Admin API still exposes a delete path for removing the record. End-user create/list/cancel is documented separately on the User API.

## Paths

| Method | Path | Purpose |
| --- | --- | --- |
| GET | `/api/share/link/list` | Get share links for all users |
| PATCH | `/api/share/link/cancel` | Cancel share link |
| DELETE | `/api/share/link/delete` | Delete external link |

These require an administrator Bearer token. The User API cancel path is also `PATCH /api/share/link/cancel` but uses a user token and a `shareUrlList` of links to cancel.

Do not treat share-download and invite-upload links as the same feature. The Admin API page titles these routes as share links; confirm `shareUrlType` or equivalent fields in the list payload before deciding whether a row is download or upload.

## Confirmation

After cancel, the link should be inaccessible. After delete, the record should no longer appear in `GET /api/share/link/list`. The Admin API does not document restoring a deleted link.
