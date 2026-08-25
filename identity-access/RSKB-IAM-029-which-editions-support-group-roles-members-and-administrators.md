---
id: RSKB-IAM-029
title: Which editions support group roles, members, and administrators?
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
- Can SMB assign administrators and role permissions within a group folder?
- Why are group roles and member permissions unavailable in Cloud?
- Does Multiple Spaces support both group administrators and member-level permissions?
keywords:
- group role permissions
- group folder members
- group folder administrators
- edition group access
legacy_ids:
- RS-FEAT-154
- RS-FEAT-156
- RS-FEAT-155
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-154 | Support group roles and set group role permissions
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-156 | Support adding administrators to the group folder
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-155 | Set group folder permission of members
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support group roles, members, and administrators?

## Short answer

Group roles, group administrators, and member permissions are each documented as SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-154
- Capability domain: Group Folders
- Original source text: Support group roles and set group role permissions
- Description: This entry describes the Raysync capability "Support group roles and set group role permissions." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 154
- Search keywords: Raysync, Group Folders, Support group roles and set group role permissions, SMB, Enterprise, Multiple Spaces

- Knowledge base ID: RS-FEAT-156
- Capability domain: Group Folders
- Original source text: Support adding administrators to the group folder
- Description: This entry describes the Raysync capability "Support adding administrators to the group folder." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.4.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 156
- Search keywords: Raysync, Group Folders, Support adding administrators to the group folder, SMB, Enterprise, Multiple Spaces

- Knowledge base ID: RS-FEAT-155
- Capability domain: Group Folders
- Original source text: Set group folder permission of members
- Description: This entry describes the Raysync capability "Set group folder permission of members." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 155
- Search keywords: Raysync, Group Folders, Set group folder permission of members, SMB, Enterprise, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
