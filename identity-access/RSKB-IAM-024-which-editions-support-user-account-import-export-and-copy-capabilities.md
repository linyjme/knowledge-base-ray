---
id: RSKB-IAM-024
title: Which editions support user account import, export, and copy capabilities?
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
- Can administrators bulk import and export accounts in Cloud?
- Why is account copying unavailable in Multiple Spaces?
- Do SMB and Enterprise support both account duplication and bulk transfer?
keywords:
- bulk account import export
- copy user accounts
- edition account operations
- administrator identity migration
legacy_ids:
- RS-FEAT-131
- RS-FEAT-132
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-131 | Copy accounts
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-132 | Import and export accounts in bulk
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support user account import, export, and copy capabilities?

## Short answer

Both copying accounts and bulk account import/export are documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-131
- Capability domain: User Management
- Original source text: Copy accounts
- Description: This entry describes the Raysync capability "Copy accounts." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise, Cloud
- Explicitly unsupported editions: Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 131
- Search keywords: Raysync, User Management, Copy accounts, SMB, Enterprise, Cloud

- Knowledge base ID: RS-FEAT-132
- Capability domain: User Management
- Original source text: Import and export accounts in bulk
- Description: This entry describes the Raysync capability "Import and export accounts in bulk." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise, Cloud
- Explicitly unsupported editions: Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 132
- Search keywords: Raysync, User Management, Import and export accounts in bulk, SMB, Enterprise, Cloud

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
