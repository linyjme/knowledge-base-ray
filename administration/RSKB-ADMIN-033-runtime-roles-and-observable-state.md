---
id: RSKB-ADMIN-033
title: Runtime roles and observable state
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
- Which role observes process state and peer connection?
- Where is live forwarding recorded?
- How are connected and completed signals attributed?
- What is the process and peer connection evidence?
- Is a live forwarding signal observable?
- How do process existence, peer connection, live forwarding, and finished-job evidence differ?
keywords: [process existing, peer connection, live forwarding, finished job, connected completed, terminal completion, role evidence]
legacy_ids: []
safety_tags: [sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-028, RSKB-ADMIN-039]
source_refs:
- {file: source_file/runtime-roles.md, section: Raysync runtime role and observable state, evidence_type: technical-boundary-document}
- {file: source_file/runtime-roles(1).md, section: Four characters, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Runtime roles and observable state

## Short answer

Each runtime state proves only its own stage. Accepted, created, running, connected, forwarding, completed, and target-verified are distinct observations and must stay distinct in an incident timeline.

## Terminology and boundaries

**Process running** proves local existence, a **peer connection** proves a channel, and **forwarding** proves traffic movement at one stage. **Terminal completion** requires the expected final state and destination evidence. The terms form an evidence ladder, not interchangeable success labels or a public service guarantee.

## State interpretation

The SDK or CLI proves parameter handling and request delivery. The manager proves task lifecycle and worker coordination. The transfer client and file service prove connection, file progress, errors, and results. The scheduler proves node-management observations. TyphoonV6 proves only its optional network-channel state and traffic.

For TyphoonV6, a running process is weaker than a connected pair, and a connected pair is weaker than a successful minimum request with bidirectional traffic. Even forwarding success does not prove the Raysync target is correct.

## Publication boundary

These state meanings are an internal diagnostic model, not a supported public contract. This article does not authorize process operations or disclosure of private runtime details, and current state names may vary by release package.
