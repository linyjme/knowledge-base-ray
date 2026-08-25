---
id: RSKB-TROUBLE-012
title: Diagnose an unreachable or repeatedly offline node
product: raysync
components:
- node-scheduler
- typhoonv6
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
- Why does a scheduler node disappear repeatedly even though its process sometimes
  exists?
- Which timeline separates network jitter, worker exits, resource pressure, and identity
  conflict?
- What proves a previously unreachable node is stably online rather than briefly reconnected?
- Why does a worker repeatedly drop out of scheduler membership?
- What causes a node to alternate between online and offline?
- Why does a scheduler worker keep dropping from its node roster?
keywords:
- node repeatedly offline
- node unreachable
- offline timeline
- status snapshot
- identity conflict
- node process
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/node-repeated-offline.md
  section: What to do if a node goes offline repeatedly
  evidence_type: technical-boundary-document
- file: source_file/node-cannot-connect.md
  section: What to do if the node cannot be connected
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose an unreachable or repeatedly offline node

## Short answer

Correlate node process, network, scheduler service, host resources, identity, and snapshot time. A brief online indication is not recovery; require stable identity and two consecutive snapshots.

## Symptoms

The node never appears, remains unconnected, or alternates online and offline while tasks interrupt or status appears to roll back.

## Checks

Preserve the offline timeline, affected tasks, process starts and exits, network events, host resource alarms, scheduler restarts, service access records, identity digest, version pair, and latest status time. Check for identity conflict before treating the event as ordinary network jitter.

## Interpretation

No server access record after an approved reachability check points to entry, policy, node configuration, or process startup. Explicit rejection points to authentication or identity mismatch. Regular disconnects aligned with process or resource events are node lifecycle failures. A stable process with stale status time points to scheduling state propagation.

## Backup or recovery boundary

Keep consecutive snapshots and both-side redacted logs as the recovery baseline. Do not repeatedly register, create a new identity to bypass rejection, or send more tasks while the node attribution is uncertain.

## Corrective action

An authorized operator must confirm the exact target node, identity, scheduler environment, and affected tasks. Confirm the expected effect, repair the first evidenced process, network, service, resource, or identity cause, and reconnect once.

## Verification

Post-action verification requires the same target identity to remain online in two consecutive snapshots, status time to advance, a read-only query to work, and a controlled task to complete or stop as expected.

## Evidence to collect

Collect versions, node role, redacted identity digest, process and connection timeline, snapshot sequence, resource event categories, and task impact. Use `<node>`, `<host>`, and `<task>` placeholders.

## Escalation

Escalate when a stable environment still cycles offline, service and node views disagree, or reconnecting produces stale or rolled-back task state.
