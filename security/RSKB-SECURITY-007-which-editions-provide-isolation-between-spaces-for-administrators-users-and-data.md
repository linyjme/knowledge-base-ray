---
id: RSKB-SECURITY-007
title: Which editions provide isolation between spaces for administrators, users, and data?
product: raysync
components: [admin-portal, file-service]
domain: security
access_level: internal
audience: [administrator, internal-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which tenant workspace isolation dimensions cover storage and integration?
- How are identities, content, and backend evidence bounded in a multi-workspace tier?
- Why must persistence and connector paths be evaluated separately?
keywords: [tenant workspace isolation storage integration, multi workspace tier identities content backend, persistence connector paths, backend boundary]
legacy_ids: [RS-FEAT-175]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-044, RSKB-ADMIN-045]
source_refs:
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-175 | Users, administrators and data in different Spaces are isolated', evidence_type: feature-matrix}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Which editions provide isolation between spaces for administrators, users, and data?

## Short answer

The supplied matrix marks isolation of users, administrators, and data between spaces as supported only in Multiple Spaces; SMB, Enterprise, and Cloud are marked not supported for this named capability.

## Terminology and boundaries

A **tenant** or workspace is the scoped organizational unit; **workspace isolation** is the matrix claim. **Identity**, **content**, **backend**, and **storage** are separate security dimensions, and an **integration boundary** can cross another system. The row does not prove end-to-end separation across every dimension.

## Security interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Isolation between spaces | Not supported | Not supported | Not supported | Supported |

This row is feature evidence, not a complete tenant-isolation threat model. It does not establish enforcement for every storage backend, integration, administrative path, or historical release. Current security publication requires product-version and cross-space authorization tests.

## Publication boundary

This internal evidence summary is not a supported public contract. It does not authorize access-policy changes and must not be used as the sole security certification for a deployment.
