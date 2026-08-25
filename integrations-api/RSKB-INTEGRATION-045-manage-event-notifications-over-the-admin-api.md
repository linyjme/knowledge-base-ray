---
id: RSKB-INTEGRATION-045
title: Manage event notifications over the Admin API
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
- How do I create a file-event rule with the Web Admin API?
- When is eventCmdProgramPath required versus httpUrl?
- Which eventType values cover sync and P2P completion?
keywords:
- /api/event/create
- eventType
- eventAction
- httpUrl
- eventCmdProgramPath
legacy_ids: []
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-040
- RSKB-ADMIN-009
- RSKB-ADMIN-011
source_refs:
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: EventResource
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Manage event notifications over the Admin API

## Short answer

Create an event with `POST /api/event/create`, list with `GET /api/event/list`, modify with `PUT /api/event/modify`, and delete with `DELETE /api/event/delete`. `eventAction` 1 runs a command and requires `eventCmdProgramPath`. `eventAction` 2 is an HTTP callback and requires `httpUrl`, `httpHeaders`, and `httpBody`.

## Paths

| Method | Path | Purpose |
| --- | --- | --- |
| POST | `/api/event/create` | Create event |
| GET | `/api/event/list` | Get event |
| DELETE | `/api/event/delete` | Delete event |
| PUT | `/api/event/modify` | Modify event |

Necessary create fields: `eventName`, `eventType`, `eventStatus` (0 disabled, 1 enable). `eventAction` defaults to 1 (command execution); 2 is HTTP callback.

## Selected eventType values

The Admin API lists numeric types. Common groups:

- File operations: 1 upload done, 2 upload failed, 3 download done, 4 download failed, 5 file delete done, 7 folder delete done, 9 folder created, 11 file renamed, 13 folder renamed
- Web transfer: 67–70 upload/download completed or failed
- Client transfer: 71–74 upload/download completed or failed
- Sync: 75–80 upload, download, and two-way completed or failed
- P2P: 81–84 send/receive completed or failed

The documentation does not define every integer between these groups. Do not invent missing types.

## Confirmation

List events after create and confirm `eventStatus` and `eventType`. Command and HTTP-callback payloads can reach local programs or external URLs; restrict `eventCmdProgramPath` and `httpUrl` to approved targets.
