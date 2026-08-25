---
id: RSKB-INTEGRATION-048
title: Query live transfer status and statistics over the Admin API
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
- How do I read live P2P or ordinary transfer status from the Admin API?
- Which statistics path returns member traffic versus space storage?
- Why does the sync live-status section reuse POST /api/machine/node?
keywords:
- /api/transmission/ptp/current
- /api/transmission/ordinary/current
- /api/transmission/web/current
- /api/statistics/flow/user
- /api/statistics/storage/space
legacy_ids: []
safety_tags:
- authorization
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-040
- RSKB-INTEGRATION-043
- RSKB-ADMIN-046
- RSKB-ADMIN-057
source_refs:
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: TransmissionResource
  evidence_type: api-reference
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: StatisticsResource
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Query live transfer status and statistics over the Admin API

## Short answer

Read live transfer snapshots from `/api/transmission/*/current`. Read usage and traffic from `/api/statistics/*`. The sync live-status heading in this Admin API document uses `POST /api/machine/node` with a nested `url` of `/api/task_list`; it does not document a `/api/transmission/synchronize/current` path.

## Live transfer paths

| Method | Path | Purpose |
| --- | --- | --- |
| GET | `/api/transmission/ptp/current` | Real-time peer-to-peer transfer |
| GET | `/api/transmission/ordinary/current` | Real-time general transfer |
| GET | `/api/transmission/web/current` | Real-time web transfer |
| POST | `/api/machine/node` | Documented under sync live status; sample `url` is `/api/task_list` |

These snapshots are observational. They do not start or stop tasks.

## Statistics paths

| Method | Path | Purpose |
| --- | --- | --- |
| GET | `/api/statistics/flow/user` | Member traffic statistics |
| GET | `/api/statistics/storage/user` | Personal file storage usage |
| GET | `/api/statistics/storage/group` | Space group file library storage usage |
| GET | `/api/statistics/storage/space` | Space file statistics |
| GET | `/api/statistics/flow/space` | Space traffic statistics |
| GET | `/api/statistics/cooperation` | Collaborative statistics |
| GET | `/api/statistics/flow/ip` | IP traffic statistics |

Redact account, IP, and volume details that are not required for the ticket. Statistics are not license-activation evidence; use `GET /api/license` for license state.
