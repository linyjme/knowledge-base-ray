---
id: RSKB-IAM-028
title: Can users belong to multiple spaces with separate storage and permissions?
product: raysync
components:
- admin-portal
domain: identity-access
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Is Multiple Spaces the only edition where one user can join several spaces?
- Can an Enterprise user receive different storage limits in separate spaces?
- Which edition keeps a user's permissions independent across multiple spaces?
keywords:
- multiple-space membership
- per-space storage limits
- separate space permissions
- administrator multi-space access
legacy_ids:
- RS-FEAT-150
- RS-FEAT-151
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-150 | Users can join multiple Spaces
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-151 | Users have different storage and permissions in different Spaces.
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Can users belong to multiple spaces with separate storage and permissions?

## Short answer

Joining multiple spaces and having separate storage and permissions in each space are documented as SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-150
- Capability domain: User Management
- Original source text: Users can join multiple Spaces
- Description: This capability is exclusive to Multiple Spaces; the other three editions are all marked as not supported.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 150
- Search keywords: Raysync, User Management, Users can join multiple Spaces, Multiple Spaces

- Knowledge base ID: RS-FEAT-151
- Capability domain: User Management
- Original source text: Users have different storage and permissions in different Spaces.
- Description: This capability is exclusive to Multiple Spaces and provides separate storage and permissions for the same user in different spaces.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 151
- Search keywords: Raysync, User Management, Users have different storage and permissions in different Spaces., Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
