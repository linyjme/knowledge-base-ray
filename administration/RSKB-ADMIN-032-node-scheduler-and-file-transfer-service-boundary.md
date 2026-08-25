---
id: RSKB-ADMIN-032
title: Node scheduler and file-transfer service boundary
product: raysync
components: [node-scheduler, file-service, admin-portal]
domain: administration
access_level: internal
audience: [internal-engineer, support-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- How are node online and transfer health signals separated?
- Where are transfers observed outside machine control?
- Can management heartbeat stay healthy as data movement services are checked separately?
keywords: [node online, transfer health signals, transfers, management heartbeat, healthy data movement services, reachability transport]
legacy_ids: []
safety_tags: [sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-030, RSKB-ADMIN-033]
source_refs:
- {file: source_file/service-boundary.md, section: Node scheduling service boundary, evidence_type: technical-boundary-document}
- {file: source_file/filetransfer-boundary.md, section: Node scheduling and filetransfer boundaries, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Node scheduler and file-transfer service boundary

## Short answer

The scheduler manages node registration, online snapshots, sessions, permissions, and management delivery. The file-transfer service owns file protocols, data movement, and file-level results. They are parallel evidence surfaces.

## Terminology and boundaries

A **management heartbeat** is a **control plane** observation about machine **reachability**. **Transfer health** belongs to the **data plane**, which has separate service and destination evidence. The sources support treating these as parallel internal paths; neither observation expands the supported public contract of the other.

## Interpretation

An online node proves only a recent scheduling connection. An accepted scheduler operation proves only that it entered the management chain. Conversely, a file failure does not prove that node registration is invalid. Record scheduler snapshot time, node report time, transfer stage, final file result, and target verification separately before attributing the fault.

Temporary snapshot lag is different from a continuously stale management state. Use consecutive observations rather than a single page status, and never replace missing transfer evidence with a healthy scheduler indicator.

## Publication boundary

This service-boundary model is not a supported public contract. It does not authorize restarting services, removing a node, modifying persistence, or treating an implementation role as a public availability promise.
