---
id: RSKB-ADMIN-045
title: Which editions support per-space administrator permissions?
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
- How are configuration boundaries separated between organizational areas?
- Which organizational area owns groups, storage, and configuration?
- Why are capacity, membership, and policy scoped independently?
- How do separate workspace users, storage, and settings relate?
- Can separate users and storage settings be scoped independently?
- Across edition evidence and matrix boundaries, how do separate workspaces assign admins, users, storage, and settings?
keywords: [separate workspaces admins users storage settings, organizational areas, groups configuration, capacity membership policy, scoped administration, tier]
legacy_ids: [RS-FEAT-172, RS-FEAT-173, RS-FEAT-174]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-044, RSKB-SECURITY-007]
source_refs:
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-172 | Administrators have different permissions in different spaces', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-173 | Supports create storages, administrators, users, groups in different spaces', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-174 | Different Spaces support different space configuration', evidence_type: feature-matrix}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Which editions support per-space administrator permissions?

## Short answer

The supplied matrix marks per-space administrator permissions, separate space objects, and different space configuration as supported only in Multiple Spaces.

## Terminology and boundaries

A **workspace** or organizational **area** is the scoped unit in this evidence. **Separate administrators**, **groups**, **storage**, and **configuration** describe dimensions that may vary by that unit. The matrix row remains uncertain internal evidence rather than a supported public isolation contract.

## Edition evidence

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Different administrator permissions by space | Not supported | Not supported | Not supported | Supported |
| Separate storage, administrators, users, and groups | Not supported | Not supported | Not supported | Supported |
| Different configuration by space | Not supported | Not supported | Not supported | Supported |

The source milestone records appearance or change, not the minimum version for this combined intent. Current entitlement and enforcement require product validation.

## Publication boundary

This internal evidence summary is not a supported public contract. It does not authorize changing role scopes, space objects, or configuration.
