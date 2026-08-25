---
id: RSKB-INTEGRATION-039
title: Configure Client API transfer proxy P2P UI and log settings
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
- How do I set Client API upload and download speed limits?
- Which path configures a SOCKS5 proxy on the Client HTTP API?
- How do I hide the Client GUI or set log retention through HTTP?
keywords:
- /set-transmission-parameters
- /set-proxy-parameters
- /set-p2p-parameters
- /set-node-machine
- /set-visible-ui
- /set-clean-log-time
legacy_ids: []
safety_tags:
- credentials
- authorization
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-010
- RSKB-INTEGRATION-035
- RSKB-INTEGRATION-036
source_refs:
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Set the maximum number of simultaneous transfer tasks
  evidence_type: api-reference
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Set transfer parameters
  evidence_type: api-reference
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Set proxy server parameters
  evidence_type: api-reference
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Set Raysync server parameters
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Configure Client API transfer proxy P2P UI and log settings

## Short answer

POST to the matching `/set-*` path, then confirm with the matching `/get-*` path. Read the current masked settings before changing a group. Do not lower TLS or copy proxy, node, or P2P secrets into logs.

## Setting catalog

Each setter is POST. Use the getter to confirm persistence.

| Set path | Get path | What it changes |
| --- | --- | --- |
| `/set-task-limit` | `/get-task-limit` | Maximum simultaneous common and P2P upload/download tasks; excess tasks queue |
| `/set-transmission-parameters` | `/get-transmission-parameters` | UDP MSS, max/min speeds, optional P2P receiver smart-speed tiers |
| `/set-advanced-parameters` | `/get-advanced-parameters` | Advanced transfer parameters |
| `/set-proxy-parameters` | `/get-proxy-parameters` | SOCKS5 or no proxy for connecting to the server |
| `/set-external-proxy-parameters` | `/get-external-proxy-parameters` | External proxy parameters |
| `/set-p2p-parameters` | `/get-p2p-parameters` | P2P transfer parameters |
| `/set-p2p-browse-config` | `/get-p2p-browse-config` | P2P browse configuration |
| `/set-node-machine` | `/get-node-machine` | Raysync server URL and authentication for the node machine |
| `/set-visible-ui` | — | Whether the graphical interface is displayed (`visible`) |
| `/set-language` | — | GUI language |
| `/set-proxy-manager` | — | Proxy manager |
| `/show-task` | — | Filter which tasks are displayed |
| `/set-clean-log-time` | `/get-clean-log-time` | Log retention / clear expired log files |
| `/set-top-task` | — | Prioritize a transfer task |
| `/set-task-speed` | — | Set task speed |

## Speed and proxy notes

`/set-transmission-parameters` requires `set-rate` and `set-min-speed`. Speeds are in Mbps; `0` means no limit. UDP `mss` range is 600–1442.

`/set-proxy-parameters` requires `proxy-type`: `none` or `socks5`. When `socks5`, `proxy-host` and `proxy-port` are required. Store `proxy-account` and `proxy-password` outside examples.

## Node machine login

`/set-node-machine` requires `enable` and `auth_way`. When `enable` is true, `url`, `account`, and `password` are required. Documented `auth_way` values:

- 1 Raysync authentication
- 2 LDAP authentication
- 4 Email authentication
- 8 System authentication
- 128 External HTTP authentication

`url` includes protocol, address, and port, for example `http://<host>:8090`.

## Confirmation

Re-read the matching getter after a settings write. A `code` of 0 does not prove the new value is active if the Client still needs a restart; the Client API documentation specifies a restart only for HTTPS certificate placement, not for every settings path. If connectivity regresses, restore only the reviewed settings group.
