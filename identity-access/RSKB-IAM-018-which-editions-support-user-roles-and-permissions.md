---
id: RSKB-IAM-018
title: Which editions support user roles and permissions?
product: raysync
components:
- admin-portal
domain: identity-access
access_level: public
audience:
- administrator
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Can administrators define roles and attach users to them in SMB?
- Do all editions support assigning permissions through user roles?
- Are role-based user permissions included in Cloud and Multiple Spaces?
keywords:
- user roles and permissions
- role-based access control
- edition authorization support
- administrator role assignment
legacy_ids:
- RS-FEAT-125
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-125 | Support user roles, set permissions for roles, and associate users
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support user roles and permissions?

## Short answer

User roles, role permissions, and associating users with roles are documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-125
- Capability domain: User Management
- Original source text: Support user roles, set permissions for roles, and associate users
- Description: This entry describes the Raysync capability "Support user roles, set permissions for roles, and associate users." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 125
- Search keywords: Raysync, User Management, Support user roles, set permissions for roles, and associate users, SMB, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
