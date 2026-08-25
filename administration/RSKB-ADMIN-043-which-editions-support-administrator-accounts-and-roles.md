---
id: RSKB-ADMIN-043
title: Which editions support administrator accounts and roles?
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
- How does the historical matrix describe multiple privileged accounts?
- Which RBAC entitlements vary by edition?
- Where are account-management capabilities qualified?
- How do product packages qualify role-based rights?
- Which edition separates administrators by role-based rights?
keywords: [product packages, administrators, role based rights, administrator permissions, multiple privileged accounts, rbac entitlement, historical matrix]
legacy_ids: [RS-FEAT-168, RS-FEAT-169]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-035]
source_refs:
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-168 | Create multiple administrators', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-169 | Support admin roles, set permissions for roles, and associate admin', evidence_type: feature-matrix}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Which editions support administrator accounts and roles?

## Short answer

The supplied matrix marks both multiple administrators and administrator roles with role permissions as supported in SMB, Enterprise, Cloud, and Multiple Spaces.

## Terminology and boundaries

**Multiple administrators** describes more than one administrative identity. **RBAC** means role-based access control, while **role rights** describe the permissions associated with a role. A **tier** is an edition row in the supplied matrix, not a current entitlement until qualified.

## Edition evidence

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Multiple administrator accounts | Supported | Supported | Supported | Supported |
| Administrator roles, permissions, and associations | Supported | Supported | Supported | Supported |

The source milestone is appearance or change evidence only; it does not establish current 8.1.8.7 support. Confirm the deployed release and entitlement before publishing a current claim.

## Publication boundary

This undated internal matrix reading is not a supported public contract. It does not authorize creating accounts, assigning roles, or expanding permissions.
