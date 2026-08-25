---
id: RSKB-INTEGRATION-038
title: Query Client API task status file lists and error codes
product: raysync
components:
- client-manager
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
- How do I list tasks from the Client HTTP API?
- Which file states appear in /get-file-list?
- What does Client API error-code 13 or 52 mean?
keywords:
- /get-task-list
- /get-task-status
- /get-file-list
- error-code
- task-group
- file-count
legacy_ids: []
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-013
- RSKB-INTEGRATION-014
- RSKB-INTEGRATION-035
- RSKB-INTEGRATION-036
source_refs:
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Check task status
  evidence_type: api-reference
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Error code description
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Query Client API task status file lists and error codes

## Short answer

POST to `/get-task-list`, `/get-task-status`, `/get-all-task-status`, `/get-file-list`, or `/get-file-list-count`. File `state` values are `waiting`, `start`, `end`, and `failed`. Use `error-code` on a failed file; `0` means no error.

## Query paths

| Path | Method | Purpose |
| --- | --- | --- |
| `/get-task-list` | POST | List tasks for a `task-group` |
| `/get-task-status` | POST | Get transfer status for selected tasks |
| `/get-all-task-status` | POST | Get status for all tasks |
| `/get-file-list-count` | POST | Count files in a task file list |
| `/get-file-list` | POST | List files in a task |
| `/get-task-type-count` | POST | Get the total number of task types |

`/get-task-list` requires `task-group`. The remarks document `all`, `normal`, `sync` (synchronization and cluster), and `p2p`. The field table types `task-group` as integer; the sample sends `"task-group": "all"`. Use the documented group names from the remarks and sample rather than inventing numeric codes.

## File list fields

Each `file-list` item includes local and remote paths, `is-folder`, `size`, `pos`, `write-time`, `state`, and `error-code`. Documented `state` values:

- `waiting` — not started
- `start` — transferring
- `end` — finished
- `failed` — failed; read `error-code`

The list response also returns operation `code`, `message`, and `file-count`. Redact full local paths before sharing lists with support.

## Selected error codes

The Client API documents codes 0–73. Frequently used values:

| Value | Name | Meaning |
| --- | --- | --- |
| 0 | ERROR_NOERROR | No error |
| 13 | ERROR_AUTH_FAILURE | Authentication failed, username or password is wrong |
| 16 | ERROR_NO_PERMISSION | Insufficient user rights |
| 19 / 20 | ERROR_LIMIT_UPLOAD / ERROR_LIMIT_DOWNLOAD | Restricted by traffic or arrears |
| 23 | ERROR_ACCOUNT_IS_LOCKED | User is locked |
| 27 | ERROR_HASH_FAULT | Hash verification error |
| 28 | ERROR_IP_IS_LOCKED | IP locked |
| 33 | ERROR_P2P_ID_NOT_FOUND | Object not found |
| 46 | ERROR_DETECTED_VIRUS | Virus detected |
| 50 | ERROR_FILE_SKIPPED | File skipped |
| 51 | ERROR_SENSITIVEWORD | Sensitive words |
| 52 | ERROR_LICENSE_EXPIRED | License invalid |
| 54 | ERROR_NO_SPACE_LEFT_ONDEVICE | Not enough disk space |
| 64 | ERROR_P2P_ID_OFFLINE | Peer-to-peer ID offline |
| 73 | ERROR_P2P_SERVICE_STATUS_STOP | P2P service exception |

Do not treat `code` 0 on the outer response as proof that every file `state` is `end`. Inspect the file list and `error-code` values.
