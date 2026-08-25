---
id: RSKB-ADMIN-041
title: Which editions support user speed and transfer-filter policies?
product: raysync
components:
- admin-portal
domain: administration
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
- Do all four editions let administrators set transfer speeds for individual users?
- Can SMB and Cloud apply transfer-file filters to a user's transfers?
- Are per-user speed controls and file-filter policies available in Multiple Spaces?
keywords:
- per-user transfer speed
- user file-filter policy
- edition availability matrix
- administrator policy controls
legacy_ids:
- RS-FEAT-134
- RS-FEAT-137
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-134 | User transfer speed settings
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-137 | Set user transfer file filtering conditions
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support user speed and transfer-filter policies?

## Short answer

Both user transfer-speed settings and user transfer-file filtering are documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

## Documented details

- Knowledge base ID: RS-FEAT-134
- Capability domain: User Management
- Original source text: User transfer speed settings
- Description: This entry describes the Raysync capability "User transfer speed settings." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 134
- Search keywords: Raysync, User Management, User transfer speed settings, SMB, Enterprise, Cloud, Multiple Spaces

- Knowledge base ID: RS-FEAT-137
- Capability domain: User Management
- Original source text: Set user transfer file filtering conditions
- Description: This entry describes the Raysync capability "Set user transfer file filtering conditions." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 137
- Search keywords: Raysync, User Management, Set user transfer file filtering conditions, SMB, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
