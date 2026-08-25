---
id: RSKB-TRANSFER-027
title: Which editions support group upload and file-filter rules?
product: raysync
components:
- admin-portal
- desktop-client
domain: transfer
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
- Can SMB skip oversized files and restrict uploads to new files?
- Which group upload and file-format rules are unavailable in Cloud?
- Does Multiple Spaces support per-user filters and file-type allowlists for group uploads?
keywords:
- group upload rules
- group file-format filters
- new-file upload restriction
- administrator transfer policy
legacy_ids:
- RS-FEAT-161
- RS-FEAT-159
- RS-FEAT-165
- RS-FEAT-160
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-161 | Skip files over set size when transferring
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-159 | Can set the associated user to upload new files only
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-165 | Black/white list of uploaded file formats
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-160 | Set file filter conditions for associated user
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support group upload and file-filter rules?

## Short answer

Skipping oversized files, upload-new-files-only policy, file-format allowlists or blocklists, and associated-user filter conditions are each documented as SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

## Documented details

- Knowledge base ID: RS-FEAT-161
- Capability domain: Group Folders
- Original source text: Skip files over set size when transferring
- Description: This entry describes the Raysync capability "Skip files over set size when transferring." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 161
- Search keywords: Raysync, Group Folders, Skip files over set size when transferring, SMB, Enterprise, Multiple Spaces

- Knowledge base ID: RS-FEAT-159
- Capability domain: Group Folders
- Original source text: Can set the associated user to upload new files only
- Description: This entry describes the Raysync capability "Can set the associated user to upload new files only." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 159
- Search keywords: Raysync, Group Folders, Can set the associated user to upload new files only, SMB, Enterprise, Multiple Spaces

- Knowledge base ID: RS-FEAT-165
- Capability domain: Group Folders
- Original source text: Black/white list of uploaded file formats
- Description: This entry describes the Raysync capability "Black/white list of uploaded file formats." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.8.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 165
- Search keywords: Raysync, Group Folders, Black/white list of uploaded file formats, SMB, Enterprise, Multiple Spaces

- Knowledge base ID: RS-FEAT-160
- Capability domain: Group Folders
- Original source text: Set file filter conditions for associated user
- Description: This entry describes the Raysync capability "Set file filter conditions for associated user." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 160
- Search keywords: Raysync, Group Folders, Set file filter conditions for associated user, SMB, Enterprise, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
