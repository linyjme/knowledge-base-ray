---
id: RSKB-TRANSFER-025
title: Which editions support user transfer priorities?
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
- Can an administrator assign transfer priorities to users in every edition?
- Does Cloud support different transfer priority levels by user?
- Are user-level transfer priorities available in SMB and Multiple Spaces?
keywords:
- user transfer priority
- per-user priority levels
- edition priority support
- administrator bandwidth policy
legacy_ids:
- RS-FEAT-152
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-152 | Support for user transfer priorities.
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support user transfer priorities?

## Short answer

User transfer priorities are documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

## Documented details

- Knowledge base ID: RS-FEAT-152
- Capability domain: User Management
- Original source text: Support for user transfer priorities.
- Description: This entry describes the Raysync capability "Support for user transfer priorities.." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 8.1.8.6
- Source location: Raysync Feature list.xlsx / English-New / row 152
- Search keywords: Raysync, User Management, Support for user transfer priorities., SMB, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
