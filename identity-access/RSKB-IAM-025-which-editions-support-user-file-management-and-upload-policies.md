---
id: RSKB-IAM-025
title: Which editions support user file-management and upload policies?
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
- Can Cloud administrators restrict a user to uploading only new files?
- Are file-format allowlists and blocklists available to users in every edition?
- Are user file-management permissions configurable in SMB and Multiple Spaces?
keywords:
- user file-management permissions
- new-file upload restriction
- transfer format allowlist
- edition upload policies
legacy_ids:
- RS-FEAT-133
- RS-FEAT-135
- RS-FEAT-136
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-133 | Set user file management permissions
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-135 | Allow users to upload new files only
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-136 | Blacklist or whitelist of user transfer file formats
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support user file-management and upload policies?

## Short answer

User file-management permissions, upload-new-files-only policy, and file-format allowlists or blocklists are each documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-133
- Capability domain: User Management
- Original source text: Set user file management permissions
- Description: This entry describes the Raysync capability "Set user file management permissions." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 133
- Search keywords: Raysync, User Management, Set user file management permissions, SMB, Enterprise, Cloud, Multiple Spaces

- Knowledge base ID: RS-FEAT-135
- Capability domain: User Management
- Original source text: Allow users to upload new files only
- Description: This entry describes the Raysync capability "Allow users to upload new files only." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 135
- Search keywords: Raysync, User Management, Allow users to upload new files only, SMB, Enterprise, Cloud, Multiple Spaces

- Knowledge base ID: RS-FEAT-136
- Capability domain: User Management
- Original source text: Blacklist or whitelist of user transfer file formats
- Description: This entry describes the Raysync capability "Blacklist or whitelist of user transfer file formats." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 136
- Search keywords: Raysync, User Management, Blacklist or whitelist of user transfer file formats, SMB, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
