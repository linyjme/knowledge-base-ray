---
id: RSKB-ADMIN-036
title: Manage the node lifecycle
product: raysync
components: [node-scheduler, admin-portal]
domain: administration
access_level: internal
audience: [administrator, internal-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which registered node remains stored after restart?
- Why is registration still weaker than reachable state?
- How are machine reboot, stale heartbeat, and online status compared?
- How are enrollment persistence, heartbeat liveness, and transport reachability divided across lifecycle stages?
- Which reboot and stored-record observations belong to enrollment, liveness, or transport stages?
keywords: [node lifecycle persistent registration reachability, registered node restart, machine record, reboot stale heartbeat online, stored enrollment liveness]
legacy_ids: []
safety_tags: [authorization, sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-035, RSKB-TROUBLE-012]
source_refs:
- {file: source_file/node-lifecycle.md, section: How the status changes, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Manage the node lifecycle

## Short answer

Registration is saved identity state; online is a fresh connection observation. A restart may preserve registration, but it invalidates any assumption that the old online snapshot proves current reachability.

## Terminology and boundaries

**Persistent registration** is a durable machine record that can survive a **reboot**. A **stale heartbeat** is weaker than current **liveness**, and neither alone proves present **reachability**. These terms separate stored lifecycle state from time-sensitive observation without promising operational availability.

## Preconditions

An authorized operator must confirm the exact target node, its stable identity summary, current lifecycle state, recent status time, affected tasks, and reason for the intended transition. Identity conflicts must be resolved before a change.

## Recovery boundary

Preserve the pre-change registration and task snapshots. Removal is not a first-line connectivity repair and must remain recoverable through the approved registration workflow; do not infer ownership from a display name alone.

## Controlled action

Confirm the exact target and effect. Perform only the approved transition, then wait for the same node identity to establish a fresh connection and publish advancing status timestamps. Avoid repeated registration or removal attempts.

## Verification

Require two consecutive fresh snapshots for the expected identity and separately verify any controlled task result. This lifecycle guidance is not a supported public contract and does not authorize undocumented node-state manipulation.
