---
id: RSKB-LICENSE-009
title: 'License administration: which License information should be checked before a system upgrade'
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
- Must I confirm the License before upgrading the product?
- How can I determine whether the current License supports the target version?
- Which activation materials should be backed up before an upgrade?
keywords:
- pre-upgrade check
- target-version entitlement
- License validity period
- activation material backup
- upgrade verification
- which License
- information should
- be checked
legacy_ids:
- KB-LICENSE-009
safety_tags:
- license-control
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/license-activation/KB-LICENSE-009-license-checks-before-upgrade.md
  section: Which License information should be checked before a system upgrade?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: which License information should be checked before a system upgrade

## Short answer

Before upgrading, confirm that the current License is activated and remains within its validity period, and ask official sales or technical support to confirm that it applies to the target version and current edition. Securely back up existing customer-visible activation materials, record limits, and schedule a maintenance window so that an entitlement mismatch is not discovered only after the upgrade.

## Scope and evidence

This applies to administrators planning a product upgrade from version 8.1.8.7. License compatibility with the target version is an upgrade prerequisite. A current page status of “Activated” alone does not prove that the License applies to an unverified target version.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

## Documented details

1. Under “Device Management > Server Management,” record the software version, License status, edition, expiration time, and maintenance expiration date.
2. Record the user count, total traffic, remaining traffic, maximum bandwidth, and edition features on which the business depends for post-upgrade comparison.
3. Confirm target-version entitlements through official upgrade notes, sales, or technical support. Obtain explicit confirmation first, especially when changing editions, maintenance has expired, or the page previously reported an unsupported version.
4. Back up the activation delivery files already held by the customer and page records according to organizational security requirements, restrict access, and do not paste complete contents into an ordinary ticket.
5. Include the upgrade, possible reactivation, and service restart in the same maintenance window, and prepare official support contact information.
6. Immediately after the upgrade, check the License status, edition, validity period, capacity limits, and important licensed features.

## Interpretation and recovery boundary

If the upgraded system reports “Current Version Not Supported” or an invalid License, stop repeatedly submitting old activation information, record the error, and contact official support. Do not perform any recovery operation not confirmed by official support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

Target-version entitlements and the support path are clear before the upgrade starts. After the upgrade, the page continues to display the correct “Activated” status, and the edition, validity period, and limits match the pre-upgrade confirmation.

## Escalation

If target-version entitlement cannot be confirmed, maintenance has expired, the upgrade includes machine migration, or the production maintenance window is insufficient, ask the product administrator to confirm with official support before upgrading. Provide the current and target versions, visible status, edition, validity period, upgrade method, and scheduled time. Do not submit the complete activation code or activation file.

