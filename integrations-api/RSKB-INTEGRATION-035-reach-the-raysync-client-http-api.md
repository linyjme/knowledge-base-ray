---
id: RSKB-INTEGRATION-035
title: Reach the Raysync Client HTTP API
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
- Where does the Raysync Client expose its local HTTP API?
- How do I enable HTTPS for the Client API listener on port 6598?
- Which certificate filenames and directories does the Client HTTP API require?
keywords:
- Client API
- 6598
- HTTPS
- certificate.pem
- private.key
- local HTTP
- Content-Type
legacy_ids: []
safety_tags:
- certificate
- credentials
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-010
- RSKB-INTEGRATION-036
- RSKB-INTEGRATION-016
source_refs:
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: Overview
  evidence_type: api-reference
- file: API/8187/Raysync Client API Documentation v8.1.8.7.md
  section: HTTPS Service
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Reach the Raysync Client HTTP API

## Short answer

Start the Raysync Client first. The Client then listens on TCP **6598** and serves the local HTTP API. HTTPS is optional and requires placing `certificate.pem` and `private.key` in the documented `config/ssl` directory for that client, then restarting the Client.

## When to use this surface

This listener is the Client HTTP control plane used by a local or otherwise authorized caller. It is not the web user portal, the web admin portal, the SDK, the synchronization CLI, or `rayfile-c`. Choose those other surfaces from `RSKB-INTEGRATION-029`.

## Reachability

1. Confirm the Raysync Client process is running on the target host.
2. Call `http://<host>:6598/<path>` with `Content-Type: application/json` unless the installed contract documents a different header.
3. For HTTPS, use `https://<host>:6598` only after the certificate files are in place and the Client has been restarted.

The documentation does not specify an authentication header for these Client API routes. Do not infer a Bearer token, and do not expose the listener beyond an approved host firewall.

## HTTPS certificate placement

Rename the certificate files to **Public key:** `certificate.pem` and **Private key:** `private.key`. Create `config/ssl` if it does not exist.

| Client | Directory |
| --- | --- |
| Windows | `C:/Program Files (x86)/Raysync Client/config/ssl` |
| Linux | `/usr/local/bin/config/ssl` |
| macOS | `/Applications/Raysync.app/Contents/RaysyncClientManager.app/Contents/MacOS/config/ssl` |
| Synchronization command-line client | `config/ssl` beside `raysync-man_cmd` |

Restart the Client after copying the files. The documentation does not specify a different listener port for HTTPS.

## Response convention

Client API operations in this documentation return `code` **0** and `message` **success** when the request is accepted. A non-zero `code` is a failure. HTTP transport success is not the same as task completion; see `RSKB-INTEGRATION-014` and `RSKB-INTEGRATION-038`.

## Related documented boundaries

- **Create tasks:** `RSKB-INTEGRATION-036`
- **Start, stop, update, and delete tasks:** `RSKB-INTEGRATION-037`
- **Query status and error codes:** `RSKB-INTEGRATION-038`
- **Change client settings:** `RSKB-INTEGRATION-039`
