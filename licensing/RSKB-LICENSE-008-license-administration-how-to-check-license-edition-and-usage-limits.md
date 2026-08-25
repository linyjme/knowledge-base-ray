---
id: RSKB-LICENSE-008
title: 'License administration: how to check License edition and usage limits'
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
- Where are licensed account-count and traffic limits displayed?
- Which entitlement fields show edition and remaining capacity?
- Does the deployment License impose a bandwidth or download-volume ceiling?
keywords:
- edition limit
- user limit
- licensed traffic
- maximum bandwidth
- feature limit
- check License
- edition capacity
- usage limits
legacy_ids:
- RS-FEAT-003
- KB-LICENSE-008
- RS-FEAT-006
safety_tags:
- license-control
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-003 | User account number
  evidence_type: feature-matrix
- file: knowledge-base/license-activation/KB-LICENSE-008-how-to-check-license-limits.md
  section: How to check License edition and usage limits?
  evidence_type: product-documentation
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-006 | Download volume
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: how to check License edition and usage limits

## Short answer

On the Server Management page, an administrator can view customer-visible information such as the current edition name, user limit, total licensed traffic, remaining traffic, maximum bandwidth, and validity period. Whether a feature is available must also be determined from the actual page entry and edition-limit message, not inferred from a single capacity field.

## Scope and evidence

This applies to capacity planning, feature evaluation, renewal and expansion, and purchasing verification in version 8.1.8.7. Editions such as Free, Professional, and Enterprise may affect available features. The page displays only entitlements currently effective in the environment.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

## Documented details

1. Go to “Device Management > Server Management” and confirm that “License Information” displays “Activated.”
2. Check the total licensed traffic and remaining traffic displayed on the page to determine whether the current capacity limit is approaching.
3. Check the user limit. If the page does not display this item, do not interpret it as a specific fixed value.
4. Check the maximum bandwidth, expiration time, and maintenance expiration date, and distinguish the License validity period from the maintenance entitlement period.
5. Use the displayed product edition name to confirm the edition. When accessing a target feature, note visible messages such as “Professional Edition or later only” or “Enterprise Edition only.”
6. Compare the page results item by item with confirmed purchasing or renewal information. Contact official sales or technical support if they differ.

## Feature-matrix evidence

### User account number

- Knowledge base ID: RS-FEAT-003
- Original source text: User account number
- Edition availability: SMB: 10; Enterprise: Unlimited; Cloud: 10; Multiple Spaces: Not specified in source
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 3

### Download volume

- Knowledge base ID: RS-FEAT-006
- Original source text: Download volume
- Edition availability: SMB: Unlimited; Enterprise: Unlimited; Cloud: Starting from 2 TB; Multiple Spaces: Not specified in source
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 6

## Interpretation and recovery boundary

If a limit is blank, a value has not updated, or the target feature still reports that the edition is unsupported, refresh the page and confirm that you are viewing the correct server. Do not determine current entitlements from an old screenshot, another server, or outdated purchasing information.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator can create a list of the current edition, validity period, user count, traffic, bandwidth, and visible feature limits, and arrange expansion or renewal before a limit is reached.

## Escalation

If capacity is nearly exhausted, business requirements exceed the current edition, or the page differs from confirmed entitlements, ask the product administrator to contact official sales or technical support. Provide the product version, edition, visible limits, and target feature name. Do not submit the complete activation code.
