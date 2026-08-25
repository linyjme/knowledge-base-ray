---
id: RSKB-LICENSE-005
title: 'License administration: what happens when a License expires'
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
- Which operations are affected by an expired License?
- Does the system stop providing services after expiration?
- What should I do when the page says the License has expired?
keywords:
- License expiration
- expiration warning
- maintenance expiration
- feature impact
- renewal
- what happens
- when a
- License expires
legacy_ids:
- KB-LICENSE-005
safety_tags:
- authorization
- license-control
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/license-activation/KB-LICENSE-005-what-happens-when-license-expires.md
  section: What happens when a License expires?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: what happens when a License expires

## Short answer

Version 8.1.8.7 displays approaching-expiration or expired warnings in the admin center, and related operations may also display a visible License-expired error. The currently available page information is insufficient to promise a uniform service shutdown or feature change for every deployment. Use the current page, actual operation results, and official support’s confirmation for that License.

## Prerequisites

This applies when an administrator receives an expiration reminder, sees a “License Expired” error, or evaluates renewal. License expiration time and the maintenance expiration date are separate page fields. A maintenance expiration warning concerns maintenance entitlements and must not be treated as equivalent to License expiration.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

## Effect

Applying updated activation information changes the License entitlement for the exact deployment and may require a service restart during a maintenance window. Checking status or warnings is read-only and does not renew the License.

## Confirmation

Confirm the exact deployment, current status and warning type, official renewal entitlement, applicable version and edition, maintenance window, and supported online or offline update path before applying it.

## Procedure

1. Go to “Device Management > Server Management” and check the expiration time and current status under “License Information.”
2. Also check whether the top of the page displays an approaching-expiration, expired, or maintenance-expiration warning, and distinguish the warning type.
3. Record the specific affected operation and its complete visible error. Do not infer that all features have stopped from a single warning.
4. Contact official sales to confirm renewal entitlement and timing, and ask technical support to confirm the actual impact on the current deployment if needed.
5. After receiving updated activation information, complete the update through the online or offline process during a maintenance window and verify the status again.

## Recovery boundary

If the page shows that the License has not expired but an operation reports expiration, refresh the status and confirm that the operation occurred on the same target server. If the page shows expiration but some features remain visible, do not infer that other features will remain available; contact official support promptly.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

The administrator can determine whether the License or maintenance entitlement has expired and obtain a renewal plan appropriate for the current edition and deployment. After the update, the page displays the new validity period and a normal status.

## Escalation

If business continuity is affected, expiration fields differ from purchasing records, or the distinction between maintenance and License expiration is unclear, ask the product administrator to escalate the issue. Provide the product version, edition, visible status, expiration fields, affected operation, and error text. Do not provide the complete activation code.
