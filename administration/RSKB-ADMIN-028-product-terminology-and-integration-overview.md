---
id: RSKB-ADMIN-028
title: Product terminology and integration overview
product: raysync
components: [client-manager, file-service, node-scheduler, cli, sdk, typhoonv6]
domain: administration
access_level: internal
audience: [internal-engineer, support-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- How are product parts grouped into internal modules and responsibilities?
- Which internal modules accept work and hand off payload?
- How do subsystem, controller, worker, payload, and proxy traffic relate?
- Can the product parts in this internal map be compared by responsibility?
- For architecture orientation, how do internal product parts, module responsibilities, and component roles relate?
keywords: [product parts, component responsibility map, internal modules, accept work, payload handoff, proxy traffic, subsystem controller worker]
legacy_ids: []
safety_tags: []
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-030, RSKB-ADMIN-033]
source_refs:
- {file: source_file/product-overview.md, section: Main characters, evidence_type: technical-boundary-document}
- {file: source_file/overview.md, section: Observability, evidence_type: technical-boundary-document}
- {file: source_file/terms.md, section: Components, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Product terminology and integration overview

## Short answer

Raysync separates task orchestration from file movement. The manager accepts and tracks work; a transfer client and file service perform file operations; node scheduling coordinates managed nodes; and TyphoonV6 may supply a network path in deployments that require it.

## Terminology and boundaries

In this internal model, **module**, **component**, **subsystem**, and **service** name bounded product parts rather than interchangeable public features. The **control plane** accepts and coordinates work; the **data plane** carries the **payload**. A **controller** coordinates a **worker**, while a **proxy** may carry **traffic** without owning the business result. These aliases organize source evidence and do not broaden a supported product contract.

## Role model

| Role | Evidence it owns | Evidence it does not own |
| --- | --- | --- |
| Client manager | request acceptance, task record, queue and status | target-file correctness |
| Transfer client | scanning, connection, progress and file results | long-term task orchestration |
| File service | remote permission and file-operation results | local task-list control |
| Node scheduler | node snapshots and management delivery | transfer-protocol success |
| TyphoonV6 | channel availability and bidirectional traffic | business permission or final task state |

Upload reads locally and writes remotely; download reads remotely and writes locally. A successful request is therefore an earlier stage than target verification.

## Publication boundary

This internal role model is not a supported public contract. It explains evidence ownership, does not authorize deployment changes, and must not be used to infer private process names, ports, protocols, or current package compatibility.
