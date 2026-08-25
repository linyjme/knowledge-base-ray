---
id: RSKB-TRANSFER-026
title: Which editions support group-folder transfer speed?
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
- Can Enterprise limit transfer speed for a group folder?
- Why are group-folder speed controls unavailable in Cloud?
- Does Multiple Spaces set different transfer speeds for associated users?
keywords:
- group-folder transfer speed
- associated-user speed limit
- edition bandwidth controls
- administrator transfer throttling
legacy_ids:
- RS-FEAT-162
- RS-FEAT-158
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-162 | Support setting speed limit
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-158 | Set group folder associated user transfer speed
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support group-folder transfer speed?

## Short answer

Both group-folder speed limits and per-associated-user transfer speed are documented as SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

## Documented details

- Knowledge base ID: RS-FEAT-162
- Capability domain: Group Folders
- Original source text: Support setting speed limit
- Description: This entry describes the Raysync capability "Support setting speed limit." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 162
- Search keywords: Raysync, Group Folders, Support setting speed limit, SMB, Enterprise, Multiple Spaces

- Knowledge base ID: RS-FEAT-158
- Capability domain: Group Folders
- Original source text: Set group folder associated user transfer speed
- Description: This entry describes the Raysync capability "Set group folder associated user transfer speed." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 158
- Search keywords: Raysync, Group Folders, Set group folder associated user transfer speed, SMB, Enterprise, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
