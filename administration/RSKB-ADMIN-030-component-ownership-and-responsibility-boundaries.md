---
id: RSKB-ADMIN-030
title: Component ownership and responsibility boundaries
product: raysync
components: [client-manager, file-service, node-scheduler, sdk, cli, typhoonv6]
domain: administration
access_level: internal
audience: [internal-engineer, support-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which team owns investigation after an accepted request?
- Do engineering job records hand off before payload starts?
- Which checkpoint separates a task record from moving bytes?
- How do component ownership and responsibility boundaries guide escalation?
keywords: [component ownership boundaries, responsibility escalation, accepted request, investigation team, engineering job record, payload starts, task handoff, moving bytes]
legacy_ids: []
safety_tags: [sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-028, RSKB-ADMIN-032]
source_refs:
- {file: source_file/component-boundaries.md, section: Component responsibilities and boundaries, evidence_type: technical-boundary-document}
- {file: source_file/responsibility-matrix.md, section: Raysync cross-engineering responsibility matrix, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Component ownership and responsibility boundaries

## Short answer

Assign a fault to the first component after the last confirmed successful stage. SDK or CLI evidence covers submission, the manager covers orchestration, the transfer client and file service cover movement and file results, and the scheduler covers node management.

## Terminology and boundaries

**Request accepted** means control acknowledged work; a **task record** means durable identity exists; **payload start** and moving **bytes** are later observations. **Ownership** follows the first missing observation, and a **handoff** transfers the evidence package rather than merely naming another team. These are internal diagnostic boundaries, not customer-facing guarantees.

## Responsibility matrix

| Component | Primary responsibility | Boundary |
| --- | --- | --- |
| SDK or CLI | parameters, request result and callbacks | acceptance is not delivery |
| Client manager | task creation, lifecycle and worker coordination | manager status is not target content |
| Transfer client | scanning, connections and data movement | progress alone is not batch success |
| File service | remote operations, permissions and results | it does not orchestrate local tasks |
| Node scheduler | registration, snapshots and management delivery | online does not mean transfer-ready |
| TyphoonV6 | optional link availability | it does not decide file permission or completion |

Keep each component's timestamped evidence separate, then correlate the records. Sanitized summaries are sufficient; raw logs, private addresses, credentials, and internal endpoints are excluded.

## Publication boundary

This responsibility matrix is not a supported public contract. It does not authorize process control, configuration changes, or bypassing a component's documented recovery workflow.
