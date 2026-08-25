---
id: RSKB-IAM-006
title: Understand administrator-restricted settings
product: raysync
components:
- user-portal
domain: identity-access
access_level: public
audience:
- end-user
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Why can I not change a permission or sync frequency myself?
- Which account settings remain under administrator control?
- Who should update a restricted role or externally managed permission?
keywords:
- restricted setting
- role
- external authentication
- sync frequency
- Why can’t I change a permission, sync frequency, or other restricted setting?
- identity access
- Raysync
legacy_ids:
- FAQ-ACCOUNT-011
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/08-user-account-and-profile.md
  section: FAQ-ACCOUNT-011 | Why can’t I change a permission, sync frequency, or other restricted setting?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand administrator-restricted settings

## Short answer

Some settings are assigned by the administrator or an external identity service and are intentionally unavailable to end users. Examples include file-operation permissions, allowed or forbidden paths, sync-filter controls, sync-task frequency, transfer priority, menu visibility, storage limits, and P2P permission.

For Raysync-managed authentication, administrators and assigned roles control access. For system or external-HTTP-controlled permissions, the Raysync default-permission setting does not take effect because the external service controls access.

## Version differences

The permission model differs across documented versions, but restricted controls remain administrator- or identity-provider-managed rather than end-user settings.

## Important notes

If a field is locked or absent, changing the client will not override the assigned policy. Ask the administrator which role, space rule, or external authentication policy applies to your account.
