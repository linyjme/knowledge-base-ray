---
id: RSKB-INTEGRATION-036
title: Create transfer sync local-copy P2P and cluster tasks with the Client API
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
- Which Client API path creates a normal upload or download?
- How do I create a synchronization task over the local HTTP API?
- What extra fields does a cluster task require compared with ordinary sync?
keywords:
- /create-task
- /create-sync-task
- /create-local-copy-task
- /create-p2p-task
- /create-cluster-task
- task-type
- triggering-condition
legacy_ids: []
safety_tags:
- credentials
- destructive-operation
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-011
- RSKB-INTEGRATION-035
- RSKB-INTEGRATION-037
- RSKB-INTEGRATION-038
source_refs:
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Create task type
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Create transfer sync local-copy P2P and cluster tasks with the Client API

## Short answer

POST JSON to the matching create path on the Client listener. Ordinary transfer, synchronization, local copy, P2P, scheduled P2P, and cluster work use different paths and required fields. A `code` of 0 means the request was accepted, not that files are complete.

## Create paths

All methods are POST. Default documented file-service values are `server-port` 2442, `server-ssl-port` 2443, and `proxy-port` 32001.

| Path | Purpose | Distinct required fields |
| --- | --- | --- |
| `/create-task` | Normal upload or download | `server-ip`, `server-port`, `server-ssl-port`, `proxy-port`, `account`, `password`, `source-path`, `target-path`, `group-id`, `task-type` (`upload` or `download`) |
| `/create-sync-task` | Synchronization | Same connection and path fields, plus `task-name`, `enable-ssl`, and `triggering-condition` (`type` required). `task-type` is `upload`, `download`, or `bidirectional`. Real-time sync only supports upload. |
| `/create-local-copy-task` | Local copy on the client | Connection and account fields, plus local `source-path` and `target-path` when `path-list` is not submitted |
| `/create-p2p-task` | One-time P2P send or receive | Connection and account fields, plus `task-name`, `p2p-id`, `task-type` (`upload` = send, `download` = receive), `source-path`, `target-path` |
| `/create-sync-p2p-task` | Scheduled or repeating P2P | Same P2P identity fields as `/create-p2p-task`, with the additional schedule fields documented on that path |
| `/create-cluster-task` | Cluster transfer | Sync-style fields plus `redis-address` and `redis-port`. `task-type` is `upload` or `download` |

Do not send a real account, password, Redis password, share-link password, or full local path in logs. Use `<account>`, `<password>`, `<path>`, and `<redis-host>`.

## Shared connection fields

Most create bodies include `server-ip`, `server-port`, `server-ssl-port`, `proxy-port`, `account`, and `password`. Optional `protocol-type` values are `default`, `tcp-first`, `tcp-only`, `udp-only`, and `auto`. When `protocol-type` is `auto`, `delay-threshold` selects TCP below the delay and UDP above it.

Optional `path-list` items can replace a single source/target pair. `full-path-pair` (alias `full_path_pair`) keeps each source as a complete source/target pair.

## Synchronization trigger and destructive options

`triggering-condition.type` values documented for `/create-sync-task` are `clock`, `interval`, `once`, `user-start-once`, `weekly-time`, and `real-time`. `clock` uses `clock` such as `08:00`. `interval` and `real-time` use `interval` in seconds. `weekly-time` uses `week` and `clock`; weekday bits are 1, 2, 4, 8, 16, 32, and 64 for Monday through Sunday, summed for multiple days.

These options can delete or move source or target content. Confirm each flag before enabling it:

- `enable-sync-remove` deletes extra files on the target. Real-time sync requires this value to be true.
- `enable-remove-on-completed` and `enable-remove-file-on-completed` delete source files after transfer. Real-time sync requires them false.
- `move-source-file` moves then later deletes uploaded sources. Real-time sync does not support source-file processing.
- `file-update-mode`: 0 overwrite, 1 append (not for object storage), 2 rename (once transfer only), 3 overwrite if source is newer. Real-time sync only supports 0.

Blacklist and whitelist wildcards cannot be enabled at the same time.

## Local copy and cluster notes

Local copy `trans-mode` values are 0 overwrite, 1 overwrite, 2 resume, and 3 skip. `parallel-files` is clamped to 1–8. `bDelete-source-after-copy` deletes the source after copy.

Cluster creation requires Redis address and port. `enable-sync-remove` on a cluster task deletes extra files on the target when enabled.

## Confirmation

Save the returned task identifier. Query `/get-task-status` or `/get-file-list` before treating the job as complete. HTTP 200 or Client `code` 0 is not completion evidence.
