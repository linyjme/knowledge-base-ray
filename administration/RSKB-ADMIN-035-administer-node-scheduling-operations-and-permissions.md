---
id: RSKB-ADMIN-035
title: Administer node scheduling operations and permissions
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
- How do authentication and authorization divide node control?
- Which managed machine scope applies to forbidden actions?
- How are identity, permission, and scheduling ownership related?
- Can I control the node in authentication or authorization?
- How are login actions on the managed machine scoped?
- How does sign-in evidence relate to node control, authentication, authorization, and access boundaries?
- How are login success, managed machine actions, forbidden scope, and permission evidence separated?
keywords: [sign in node control, authentication authorization, login managed machine, forbidden actions scope, identity permission]
legacy_ids: []
safety_tags: [authorization, sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-036, RSKB-TROUBLE-015]
source_refs:
- {file: source_file/administrator-operations.md, section: Node scheduling administrator operations, evidence_type: technical-boundary-document}
- {file: source_file/session-permissions.md, section: User session and node scheduling permissions, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Administer node scheduling operations and permissions

## Short answer

Separate session validity from authorization. A valid session permits authentication; the assigned role and resource scope determine which nodes and task controls the operator may use.

## Terminology and boundaries

**Login** and **authentication** establish identity. A **forbidden action** is evaluated by **authorization**, including the effective **node scope**. This distinction explains an internal permission boundary; it does not grant a role, expand scope, or authorize a production change.

## Preconditions

An authorized administrator must confirm the exact target node, affected user or role, requested permission, reason, impact, and rollback owner. Preserve a redacted node-identity summary, current role scope, online snapshot, and affected-task inventory.

## Recovery boundary

Keep the previous authorization and display-state summary so it can be restored through the approved administration workflow. Do not copy another identity, remove registration as a connection test, or widen scope to diagnose one denial.

## Controlled action

Confirm the exact target and effect, then change only the smallest approved role or node scope. Ask the affected operator to establish a fresh session before testing a read-only view and one reversible control within that scope.

## Verification

Verify the intended node is visible, unrelated nodes remain unavailable, the permitted action succeeds once, and a prohibited action remains denied. Record the result in the audit trail. This internal procedure is not a supported public contract and does not authorize undocumented controls.
