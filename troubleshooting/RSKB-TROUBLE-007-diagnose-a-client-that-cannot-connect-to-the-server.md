---
id: RSKB-TROUBLE-007
title: Diagnose a client that cannot connect to the server
product: raysync
components:
- desktop-client
- file-service
domain: troubleshooting
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: null
  to: null
version_status: uncertain
status: active
question_variants:
- Why is the browser portal reachable while the desktop transfer client remains disconnected?
- What evidence separates a stopped server process from a blocked client-to-server
  path?
- How can support distinguish certificate trust, network reachability, and service
  rejection?
- After the web page opens, which check explains an offline transfer app?
keywords:
- client disconnected
- server access record
- portal reachable
- connection rejection
- certificate trust
- service process
legacy_ids:
- KB-SERVICE-008
safety_tags:
- sensitive-diagnostics
- authorization
- certificate
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/client-cannot-connect.md
  section: What to do if the client cannot connect to the server
  evidence_type: technical-boundary-document
- file: knowledge-base/service-configuration/KB-SERVICE-008-client-cannot-connect-to-server.md
  section: How to troubleshoot a client that cannot connect to the server?
  evidence_type: validated-faq
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose a client that cannot connect to the server

## Short answer

Separate server availability, client process state, network reachability, certificate trust, and server rejection. A running client or reachable browser page alone does not prove that the transfer connection succeeded.

## Symptoms

The desktop client stays disconnected, the local portal is unavailable, or connection attempts fail quickly. Record whether the browser can reach the approved service entry, whether the client process is running, and whether a small transfer can start.

## Checks

Without changing state, compare client and server versions and time windows. Confirm the client process and server process are stable, use an organization-approved reachability check, and compare redacted records for a client attempt and a server access record. If the browser works but the client fails, inspect client startup, proxy, certificate trust, account scope, and transfer permission. If both sides report connected but requests fail, treat it as connected but no traffic rather than a connection-stage failure.

## Interpretation

No stable server process indicates service or host trouble. A client attempt without a server access record indicates the address, route, firewall, or proxy path. An immediate server rejection points to version, identity, certificate, authentication, or policy. A completed connection with failed application traffic belongs to the data or target-service stage.

## Backup or recovery boundary

Preserve the original status and redacted timeline as the recovery baseline. Do not weaken certificate validation, copy an old deployment configuration, or restart first; keep a known-good configuration snapshot and reverse only the single confirmed change.

## Corrective action

An authorized operator must confirm the exact target client, server, account scope, and service entry. Confirm the intended effect before correcting one evidenced cause: start the documented service safely, restore the approved entry, correct supported proxy or certificate trust, or restore the required permission. Reconnect once after confirmation.

## Verification

Post-action verification requires the same target to show a stable client process, a matching server access record, connected state, and one small non-sensitive transfer reaching terminal state with target-file verification.

## Evidence to collect

Collect version and platform categories, time zone, connection stage, masked failure category, and a short timeline from both roles. Use `<host>`, `<account>`, `<path>`, and `<token>` placeholders; never share real addresses, credentials, full settings, certificates, or full logs.

## Escalation

Escalate when the approved path is reachable but the server still rejects the client, when multiple users fail, or when the service cannot remain stable. Include completed checks and the first failed stage.
