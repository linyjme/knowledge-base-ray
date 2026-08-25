---
id: RSKB-INTEGRATION-037
title: Start stop update and delete Client API tasks
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
- How do I start or stop a task created through the Client HTTP API?
- How do I enable the P2P receiver monitor before a peer can connect?
- Does deleting a Client API task delete the remote files?
keywords:
- /start-task
- /stop-task
- /delete-task
- /update-task
- /enable-p2p-monitor
- task-id
legacy_ids: []
safety_tags:
- credentials
- destructive-operation
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-012
- RSKB-INTEGRATION-035
- RSKB-INTEGRATION-036
- RSKB-INTEGRATION-038
source_refs:
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: P2P transfer
  evidence_type: api-reference
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Delete tasks
  evidence_type: api-reference
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Control task
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Start stop update and delete Client API tasks

## Short answer

POST to the documented control path with the task identifier. Enable `/enable-p2p-monitor` on the receiver before a sender can connect. Query status after start, stop, or update. Deleting a task record is not documented as deleting remote files.

## P2P monitor

| Path | Method | Purpose |
| --- | --- | --- |
| `/enable-p2p-monitor` | POST | Enable the receiver P2P monitor. The receiver can establish a connection only after this is enabled. If multiple servers are available, enable the monitor on each. The sender does not need the monitor enabled. |
| `/disable-p2p-monitor` | POST | Disable the receiver P2P monitor |

Both bodies require `server-ip`, `server-port`, `server-ssl-port`, `proxy-port`, `account`, and `password`.

## Task control

| Path | Method | Purpose |
| --- | --- | --- |
| `/start-task` | POST | Start one task |
| `/start-all-task` | POST | Start all tasks |
| `/stop-task` | POST | Stop one task |
| `/stop-all-task` | POST | Stop all tasks |
| `/update-task` | POST | Update an existing task by ID |
| `/delete-task` | POST | Delete one or more tasks by ID |
| `/delete-all-task` | POST | Delete all tasks |

Do not use an all-tasks start, stop, or delete call as a connectivity probe.

The `/delete-task` field table marks both `task-id` and `task-ids` as necessary. The samples submit **either** `{ "task-id": 1 }` **or** `{ "task-ids": "1,2" }`. The documentation does not specify what happens if both are sent.

`/update-task` requires `update-tasks[]` items that include `task-id`, `server-ip`, `protocol-type`, `enable-ssl`, `enable-verify-hash`, and `delete-database`. Confirm `delete-database` before sending it.

## Confirmation

Re-read `/get-task-status` or `/get-task-list` after a control call. A `code` of 0 means the control request was accepted. Batch or all-task calls may still leave individual tasks unchanged; inspect each selected task.

## Recovery boundary

Keep the previous task configuration and target-file evidence before delete. The Client API documents deleting a task by ID. It does not document that this removes files on the server or peer.
