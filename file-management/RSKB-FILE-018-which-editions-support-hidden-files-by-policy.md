---
id: RSKB-FILE-018
title: Which editions support hidden files by policy?
product: raysync
components:
- admin-portal
- user-portal
domain: file-management
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
- Can administrators hide hidden files from users in every edition?
- Does the Cloud edition support a policy that suppresses hidden files?
- Is the hidden-file visibility control available in SMB and Multiple Spaces?
keywords:
- hidden-file visibility policy
- suppress hidden files
- edition policy availability
- administrator file display control
legacy_ids:
- RS-FEAT-142
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-142 | Support not showing hidden files
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support hidden files by policy?

## Short answer

The policy for not showing hidden files is documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

## Documented details

- Knowledge base ID: RS-FEAT-142
- Capability domain: User Management
- Original source text: Support not showing hidden files
- Description: This entry describes the Raysync capability "Support not showing hidden files." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 142
- Search keywords: Raysync, User Management, Support not showing hidden files, SMB, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
