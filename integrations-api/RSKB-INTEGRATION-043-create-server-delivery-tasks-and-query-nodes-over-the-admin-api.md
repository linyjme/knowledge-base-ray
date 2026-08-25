---
id: RSKB-INTEGRATION-043
title: Create server delivery tasks and query nodes over the Admin API
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
- How do I create a server delivery or synchronization task from the Admin API?
- Which triggeringCondition values does task distribution accept?
- How do I query node information through POST /api/machine/node?
keywords:
- /api/task_distribution/create
- /api/task_distribution/list
- /api/task_distribution/delete
- /api/machine/node
- triggeringCondition
- sourceIsClient
legacy_ids: []
safety_tags:
- authorization
- destructive-operation
- credentials
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-040
- RSKB-TRANSFER-016
- RSKB-SYNC-018
- RSKB-ADMIN-036
source_refs:
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: TaskDistributionResource
  evidence_type: api-reference
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: NodeResource
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Create server delivery tasks and query nodes over the Admin API

## Short answer

Create a server delivery or synchronization task with `POST /api/task_distribution/create`, list with `GET /api/task_distribution/list`, and delete with `DELETE /api/task_distribution/delete`. Query nodes with `POST /api/machine/node`. Confirm `removeSurplusFile` and source-deletion options before enabling them.

## Delivery task paths

| Method | Path | Purpose |
| --- | --- | --- |
| POST | `/api/task_distribution/create` | Create a server delivery task |
| GET | `/api/task_distribution/list` | List server delivery tasks |
| DELETE | `/api/task_distribution/delete` | Delete a server delivery task |

Necessary create fields include `taskName`, `sourcePath`, `storageId`, `spaceId`, `targetPath`, `taskType`, and `triggeringCondition`. `taskType` values are `Upload`, `Download`, and `Bidirectional`.

`sourcePath` and `targetPath` are absolute. When the server side is involved, the path is relative to the location pointed to by `storageId`.

## Trigger types

`triggeringCondition.taskFrequencyType` values:

- `once` — run once; includes an `once` timestamp
- `integer` — repeat every N seconds (`integer`: 3600 is once per hour)
- `clock` — run daily at `clock` such as `08:00`
- `timing` — weekly; `week` bits 1, 2, 4, 8, 16, 32, 64 for Monday–Sunday, plus `clock`

The documentation also lists `sourceIsClient` to indicate whether the source is the client.

## Destructive sync options

These create fields can delete or move files. Enable them only with explicit authorization:

- `removeSurplusFile` — delete extra target files when the source is deleted
- `syncRemoveSourceFile` / `syncRemoveSourceFileDetail` — delete or move source files after transfer
- `fileUpdatedMode` — 0 overwrite, 1 append (not object storage), 2 rename (once tasks only), 3 overwrite if source is newer

`fullSync`, `saveTimestamp`, and `enable_save_acl` are documented as a choose-one group for preserving attributes, while `saveTimestamp` and `enable_save_acl` may be enabled together.

## Node query

`POST /api/machine/node` is documented twice in the Admin API: under NodeResource and again under “Get real-time information of sync transfer”. The second listing’s sample body is `{ "url": "/api/task_list", "headers": { "Content-Type": "application/json;charset=UTF-8" } }`. Treat that as a documented request shape for that section; do not invent a different sync-status path.
