---
id: RSKB-STORAGE-011
title: Which editions support group-folder storage quotas?
product: raysync
components:
- admin-portal
- file-service
domain: storage
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
- Can Enterprise enforce a maximum capacity for Group files?
- Is a group-folder storage quota supported by Cloud?
- Do SMB and Multiple Spaces provide configurable group-storage limits?
keywords:
- group-folder storage quota
- group-file capacity limit
- edition quota support
- administrator storage controls
legacy_ids:
- RS-FEAT-166
- RS-FEAT-164
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-166 | Maximum storage limit for Group files
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-164 | Support setting maximum storage capacity
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support group-folder storage quotas?

## Short answer

Both the maximum limit for Group files and configurable maximum group-storage capacity are documented as SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-166
- Capability domain: Group Folders
- Original source text: Maximum storage limit for Group files
- Description: This entry describes the Raysync capability "Maximum storage limit for Group files." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 166
- Search keywords: Raysync, Group Folders, Maximum storage limit for Group files, SMB, Enterprise, Multiple Spaces

- Knowledge base ID: RS-FEAT-164
- Capability domain: Group Folders
- Original source text: Support setting maximum storage capacity
- Description: This entry describes the Raysync capability "Support setting maximum storage capacity." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 164
- Search keywords: Raysync, Group Folders, Support setting maximum storage capacity, SMB, Enterprise, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
