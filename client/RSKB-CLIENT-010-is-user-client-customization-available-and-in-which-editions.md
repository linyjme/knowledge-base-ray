---
id: RSKB-CLIENT-010
title: Is user client customization available, and in which editions?
product: raysync
components:
- desktop-client
- client-manager
domain: client
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
- Can Enterprise deployments customize the end-user desktop client?
- Is client branding or customization included with SMB?
- Do Cloud and Multiple Spaces support a customized user client?
keywords:
- end-user client customization
- desktop client branding
- edition customization availability
- administrator deployment options
legacy_ids:
- RS-FEAT-216
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-216 | User client customization
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Is user client customization available, and in which editions?

## Short answer

User-client customization is documented as SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

## Documented details

- Knowledge base ID: RS-FEAT-216
- Capability domain: Customized Services
- Original source text: User client customization
- Description: This entry describes the Raysync capability "User client customization." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 216
- Search keywords: Raysync, Customized Services, User client customization, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
