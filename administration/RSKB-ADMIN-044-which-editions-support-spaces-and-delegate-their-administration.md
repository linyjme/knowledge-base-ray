---
id: RSKB-ADMIN-044
title: Which editions support spaces and delegate their administration?
product: raysync
components: [admin-portal]
domain: administration
access_level: internal
audience: [administrator, internal-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- How are assigned workspaces bounded within a product package?
- What does delegated administration mean for an organizational area?
- Why is allocated workspace evidence edition-specific?
keywords: [assigned workspaces product package, delegated organizational area, allocated workspace, edition scope]
legacy_ids: [RS-FEAT-170, RS-FEAT-171]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-045, RSKB-SECURITY-007]
source_refs:
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-170 | Supports creating multiple spaces and assigning them to administrators', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-171 | Administrators can manage multiple spaces, administrators can only view the administrators, users, configurations, logs, etc. of their assigned space.', evidence_type: feature-matrix}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Which editions support spaces and delegate their administration?

## Short answer

The supplied matrix marks creation and administrator assignment of multiple spaces, plus assigned-space visibility, as supported only in Multiple Spaces.

## Terminology and boundaries

A **delegated administrator** manages a bounded assignment. The **assigned organizational area** is the source concept represented here as a space, and **workspace scope** is a useful internal alias for that visibility boundary. These terms interpret the matrix and do not establish a broader entitlement.

## Edition evidence

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Create spaces and assign administrators | Not supported | Not supported | Not supported | Supported |
| Limit administrators to assigned-space objects | Not supported | Not supported | Not supported | Supported |

The row's historical milestone does not prove current availability. Assigned-space visibility is evidence for an administrative boundary, not evidence that every possible data path has been security-tested.

## Publication boundary

This internal matrix interpretation is not a supported public contract. It does not authorize space creation, delegation, or access changes.
