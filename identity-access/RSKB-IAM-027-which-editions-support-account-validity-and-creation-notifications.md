---
id: RSKB-IAM-027
title: Which editions support account validity and creation notifications?
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
- Can every edition set an expiration period for user accounts?
- Does Cloud send an email when an account is created?
- Are account-validity controls and creation notices supported in Multiple Spaces?
keywords:
- account validity periods
- account creation email
- edition lifecycle notifications
- administrator expiration policy
legacy_ids:
- RS-FEAT-147
- RS-FEAT-148
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-147 | Account validity period settings
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-148 | Create account email notification
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support account validity and creation notifications?

## Short answer

Both account-validity settings and account-creation email notifications are documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-147
- Capability domain: User Management
- Original source text: Account validity period settings
- Description: This entry describes the Raysync capability "Account validity period settings." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.1
- Source location: Raysync Feature list.xlsx / English-New / row 147
- Search keywords: Raysync, User Management, Account validity period settings, SMB, Enterprise, Cloud, Multiple Spaces

- Knowledge base ID: RS-FEAT-148
- Capability domain: User Management
- Original source text: Create account email notification
- Description: This entry describes the Raysync capability "Create account email notification." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.1
- Source location: Raysync Feature list.xlsx / English-New / row 148
- Search keywords: Raysync, User Management, Create account email notification, SMB, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
