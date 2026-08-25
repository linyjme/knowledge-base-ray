---
id: RSKB-ADMIN-055
title: Which editions support portal navigation and access?
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
- Which editions let an administrator hide items from the user portal menu?
- Can Cloud disable access to the user portal or external-link portal?
- Are portal navigation controls available in Enterprise but unavailable in SMB?
keywords:
- user portal navigation
- external-link portal access
- edition access controls
- administrator menu customization
legacy_ids:
- RS-FEAT-218
- RS-FEAT-217
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-218 | Disable/enable access to the user portal and external link portal
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-217 | Support admin portal to customize the left menu bar of user portal
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support portal navigation and access?

## Short answer

Both portal-access controls and user-portal menu customization are documented as SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

## Documented details

- Knowledge base ID: RS-FEAT-218
- Capability domain: Customized Services
- Original source text: Disable/enable access to the user portal and external link portal
- Description: This entry describes the Raysync capability "Disable/enable access to the user portal and external link portal." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.7.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 218
- Search keywords: Raysync, Customized Services, Disable/enable access to the user portal and external link portal, Enterprise, Cloud, Multiple Spaces

- Knowledge base ID: RS-FEAT-217
- Capability domain: Customized Services
- Original source text: Support admin portal to customize the left menu bar of user portal
- Description: This entry describes the Raysync capability "Support admin portal to customize the left menu bar of user portal." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.4.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 217
- Search keywords: Raysync, Customized Services, Support admin portal to customize the left menu bar of user portal, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
