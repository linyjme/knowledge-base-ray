---
id: RSKB-INTEGRATION-046
title: Query transfer logs over the Admin API
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
- How do I download a single transfer log from the Admin API?
- Which log path is for P2P versus sync versus web transfer?
- How should I redact Admin API log responses before sharing them?
keywords:
- /api/logs/transmission/detail
- /api/logs/transmission/ptp
- /api/logs/transmission/ordinary
- /api/logs/transmission/synchronize
- /api/logs/transmission/web
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-040
- RSKB-TROUBLE-009
- RSKB-ADMIN-056
source_refs:
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: LogsResource
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Query transfer logs over the Admin API

## Short answer

Use the `/api/logs/transmission/*` GET routes for the matching transfer class. `GET /api/logs/transmission/detail` returns details; `GET /api/logs/transmission/download` returns a single transfer log. Redact accounts, paths, and addresses before sharing.

## Paths

| Method | Path | Purpose |
| --- | --- | --- |
| GET | `/api/logs/transmission/detail` | Transfer log details |
| GET | `/api/logs/transmission/download` | Single transfer log |
| GET | `/api/logs/transmission/ptp` | Peer-to-peer transfer logs |
| GET | `/api/logs/transmission/ordinary` | General transfer logs |
| GET | `/api/logs/user/trans_log/get_all` | All transfer logs |
| GET | `/api/logs/transmission/synchronize` | Sync transfer logs |
| GET | `/api/logs/transmission/web` | Web transfer logs |

All require an administrator Bearer token.

## Sharing boundary

Log bodies can contain user identifiers, file paths, and network details. Follow `RSKB-TROUBLE-009`: share only sanitized excerpts, and do not paste raw log API responses into public tickets.
