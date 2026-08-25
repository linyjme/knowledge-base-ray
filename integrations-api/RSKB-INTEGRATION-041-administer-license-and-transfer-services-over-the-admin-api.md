---
id: RSKB-INTEGRATION-041
title: Administer license and transfer services over the Admin API
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
- How do I read license information from the Web Admin API?
- Which Admin API path returns transfer service status?
- How do I restart the transfer service through the Admin API?
keywords:
- /api/license
- /api/service/status
- /api/service/transfer/restart
- Admin API
legacy_ids: []
safety_tags:
- license-control
- authorization
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-040
- RSKB-LICENSE-001
- RSKB-ADMIN-018
- RSKB-ADMIN-019
source_refs:
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: LicenseResource
  evidence_type: api-reference
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: ServiceResource
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Administer license and transfer services over the Admin API

## Short answer

Send `Authorization: Bearer <token>` after admin login. `GET /api/license` returns license information. `GET /api/service/status` returns service status. `POST /api/service/transfer/restart` restarts the transfer service. Confirm status after a restart; do not treat HTTP 200 alone as proof that transfers are healthy.

## Paths

| Method | Path | Purpose |
| --- | --- | --- |
| GET | `/api/license` | Get license information |
| GET | `/api/service/status` | Get the status of the service |
| POST | `/api/service/transfer/restart` | Restart the transfer service |

These routes require an administrator token from `RSKB-INTEGRATION-040`. Restarting a service is an administrator operation and can interrupt active transfers.

## Confirmation

After restart, call `GET /api/service/status` again. Pair the API result with the administrator procedures in `RSKB-ADMIN-018` and `RSKB-ADMIN-019` rather than inferring ports or process names that this API document does not list.
