---
id: RSKB-TROUBLE-016
title: Diagnose web management and node connection
product: raysync
components:
- admin-portal
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
- Why can the management page work while the expected node is absent from its list?
- What separates management-plane authorization from node-connection health?
- Why does an online scheduler node not prove that a user's operation or file task
  succeeded?
- Why can the admin page work while the execution node is missing?
- Why is a connected node unavailable for scheduler dispatch?
keywords:
- management plane
- node connection plane
- node missing
- management authorization
- latest node update
- plane mismatch
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/web-node-connection.md
  section: Web management and node connection
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose web management and node connection

## Short answer

The management plane and node connection plane are different entries. Test the user's read-only management access and the node's latest connection update separately; node online does not mean task success or management authorization.

## Symptoms

The page is unavailable, login or queries fail, the page works but the node is missing, or the node is online while a state change is denied.

## Checks

Use the same user for a read-only query and record visible scope and time. Separately check the exact node identity, process, connection record, and latest status update. Compare the page and scheduler snapshots without repeated refresh or reconnect. Then inspect task final state and target evidence separately.

## Interpretation

Management failure points to session, role, or management service. A normal page with a missing node points to node process, network, identity, or connection. An online node with a denied action points to authorization. An online node with a failed transfer belongs to task or file service, not scheduling presence.

## Backup or recovery boundary

Keep management and node snapshots from the same time window as the recovery baseline. Do not grant permission merely to make views agree, reconnect repeatedly, or treat either plane as proof of target success.

## Corrective action

An authorized operator must confirm the exact target plane, user, node identity, requested operation, and expected effect. Confirm whether the correction belongs to session, management service, node connection, or authorization, and change only that evidenced layer.

## Verification

Post-action verification requires the same target user to complete a read-only query, the expected node to show a fresh stable update, any authorized operation to have an audit result, and the task to reach independently verified target evidence.

## Evidence to collect

Collect redacted user-role category, management result, node identity digest, connection and status times, audit category, task state, and target result. Use `<user>`, `<node>`, and `<task>` placeholders.

## Escalation

Escalate when plane snapshots remain inconsistent, the node update is stale despite a live connection, or authorization results differ across management entries.
