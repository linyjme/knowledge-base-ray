---
id: RSKB-IAM-022
title: Which editions support Linux operating-system users?
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
- Which edition can authenticate users against Linux server accounts?
- Can Cloud users sign in with operating-system credentials?
- Is Linux system-user authentication restricted to Enterprise?
keywords:
- Linux system-user authentication
- operating-system credentials
- Enterprise identity integration
- administrator Linux login
legacy_ids:
- RS-FEAT-129
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-129 | Support authentication by server operating system user (Linux server version only)
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support Linux operating-system users?

## Short answer

Authentication with Linux server operating-system users is documented as SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-129
- Capability domain: User Management
- Original source text: Support authentication by server operating system user (Linux server version only)
- Description: This entry describes the Raysync capability "Support authentication by server operating system user (Linux server version only)." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Explicitly supported editions: Enterprise
- Explicitly unsupported editions: SMB, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 129
- Search keywords: Raysync, User Management, Support authentication by server operating system user (Linux server version only), Enterprise

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
