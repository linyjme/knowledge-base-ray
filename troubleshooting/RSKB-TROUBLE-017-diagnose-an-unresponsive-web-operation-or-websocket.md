---
id: RSKB-TROUBLE-017
title: Diagnose an unresponsive web operation or WebSocket
product: raysync
components:
- admin-portal
- client-manager
- http-api
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
- Why does a browser operation keep spinning after its secure socket handshake?
- Which observation separates no WebSocket handshake, no response frame, and stale
  page rendering?
- What proves that one click created and completed only one intended task?
- Why does the browser stay busy after its socket connection opens?
- Why does the page stop updating after a WebSocket handshake?
- Why does a browser keep loading when its connection socket is already open?
keywords:
- web operation unresponsive
- secure WebSocket handshake
- response frame
- page status subscription
- duplicate submission
- manager processing
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
- certificate
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/websocket-no-response.md
  section: Web page operation is unresponsive
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose an unresponsive web operation or WebSocket

## Short answer

Separate secure WebSocket handshake, maintained connection, response frames, manager processing, and page status subscription. A responsive button or accepted request does not prove task completion.

## Symptoms

A create, query, or control operation spins indefinitely, the secure socket reconnects repeatedly, or the response arrives while the page remains stale.

## Checks

Preserve the operation time and avoid repeated submission. Confirm the local manager with a read-only query, inspect only secure WebSocket handshake and response-frame categories, compare proxy, extension, certificate trust, page host, and manager environment, then inspect task parameters, queue, manager resources, and page status subscription. Compare a supported read-only entry without using it to bypass the page.

## Interpretation

No secure WebSocket handshake indicates listener, network, certificate, or browser environment. A maintained connection without a response frame indicates request delivery or manager processing. A received response with stale rendering indicates subscription, refresh, or cache. One affected task indicates parameters or queue rather than global service failure.

## Backup or recovery boundary

Save the original page, handshake category, response category, and task list as the recovery baseline. Do not click repeatedly, bypass browser security, replace certificates manually, or submit a duplicate task. Reconnect the page once only after the scene is preserved.

## Corrective action

An authorized operator must confirm the exact target page, manager, operation, and existing task list. Confirm the intended effect and duplicate risk, then correct one evidenced browser, proxy, certificate-trust, manager, queue, or task-parameter cause.

## Verification

Post-action verification requires the same target read-only query to return, one request to map to one task, acceptance through terminal state to be visible, page and manager state to agree, and target verification to succeed.

## Evidence to collect

Collect masked browser and manager versions, entry type, time window, handshake category, response-frame category, queue state, and screenshot with private values removed. Use `<host>`, `<task>`, and `<path>` placeholders.

## Escalation

Escalate when the manager is healthy but frames never return, page and manager states remain inconsistent, or duplicate task creation may have occurred.
