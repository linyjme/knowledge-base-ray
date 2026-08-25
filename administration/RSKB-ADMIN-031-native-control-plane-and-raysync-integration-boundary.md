---
id: RSKB-ADMIN-031
title: Native control-plane and Raysync integration boundary
product: raysync
components: [client-manager, file-service, sdk, cli, typhoonv6]
domain: administration
access_level: internal
audience: [internal-engineer, developer, support-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which boundary separates proxy traffic from application failure?
- How are tunnel directions and forwarding observed?
- Why can transfer traffic pass while the application fails?
- What does the proxy do at the transfer integration boundary?
- How is traffic observed in the application boundary?
- How is passing proxy traffic distinguished from a transfer that still fails at the application boundary?
keywords: [passing proxy traffic, transfer still fails, tunnel directions, forwarding boundary, application failure, native control plane, business operation]
legacy_ids: []
safety_tags: [sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-030, RSKB-INTEGRATION-002]
source_refs:
- {file: source_file/control-plane-boundary.md, section: Responsibilities and boundaries of native control plane, evidence_type: technical-boundary-document}
- {file: source_file/raysync-integration-boundary.md, section: Integration boundary between TyphoonV6 and Raysync, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Native control-plane and Raysync integration boundary

## Short answer

The native manager orchestrates tasks and workers; it does not move remote file bytes. TyphoonV6 may forward traffic, but Raysync components still own task selection, permission, file results, and business completion.

## Terminology and boundaries

A **proxy** or **tunnel** can establish **bidirectional traffic** and **forwarding**. That transport observation remains separate from an **application failure** and its business result. The **boundary** is crossed only when controller, transport, worker, and destination evidence are correlated; channel health alone does not prove completion.

## Observable chain

Follow request acceptance, task persistence, worker registration, connection or traffic, final task state, and target verification. A missing worker points to the manager-to-worker boundary. Bidirectional proxy traffic with a failed business result points beyond the forwarding layer. Neither signal proves the other.

Integrations may use the exposed GUI, CLI, SDK, or supported forwarding entrance. They must not depend on undisclosed messages, private process names, or inferred fixed network details.

## Publication boundary

This implementation explanation is not a supported public contract. It does not authorize changing a production process, proxy, routing policy, or transfer destination; current integration support requires release-specific product evidence.
