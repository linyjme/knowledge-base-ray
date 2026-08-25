---
id: RSKB-LICENSE-001
title: 'License administration: how to check the current License status'
product: raysync
components:
- admin-portal
domain: licensing
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
- Where can I see whether the License is activated?
- How can I confirm the current edition?
- When does the License expire?
keywords:
- License status
- edition
- expiration time
- licensed traffic
- user limit
- check the
- current License
- status
legacy_ids:
- KB-LICENSE-001
safety_tags:
- license-control
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/license-activation/KB-LICENSE-001-how-to-check-license-status.md
  section: How to check the current License status?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: how to check the current License status

## Short answer

An administrator can view the activated or not activated status under “License Information” in “Device Management > Server Management,” together with the validity period, capacity, and user limits actually displayed on the page. The product version under Server Information and the edition name shown on the page can be used to confirm the current software version and edition.

## Scope and evidence

This applies to routine checks, renewal preparation, capacity verification, or pre-upgrade checks by product administrators in version 8.1.8.7. The page displays only information currently effective in the environment. If purchased entitlements differ from the page, obtain confirmation from official sales or technical support.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

## Documented details

1. Sign in to the admin center with an administrator account and open “Device Management > Server Management.”
2. Check the status under “License Information.” The page displays “Activated” or “Not Activated.”
3. Expand or view the License details and record the visible activation time, expiration time, and maintenance expiration date.
4. Based on what is actually displayed, verify total licensed traffic, remaining traffic, user limit, and maximum bandwidth. Do not assume that an item not displayed is unlimited.
5. Check the product version under “Server Information” on the same page, and use the displayed Free, Professional, or Enterprise edition name to confirm the edition.

## Interpretation and recovery boundary

Refresh the page, sign in to the admin center again, and confirm that you are viewing the target server. If fields are empty, the status conflicts with actual use, or the edition cannot be confirmed, retain a non-sensitive screenshot of the current page. Do not include the complete activation code in the screenshot.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator can confirm the current License status, software version, edition, validity period, and publicly displayed capacity limits, then decide whether renewal, expansion, or support is required.

## Escalation

If a non-administrator cannot access Server Management, the status does not refresh for an extended period, or purchasing information differs from the page, ask the product administrator to contact official sales or technical support. Provide the product version, visible status, edition, and relevant time fields only.

