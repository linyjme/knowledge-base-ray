---
id: RSKB-LICENSE-006
title: 'License administration: how to update or replace a License'
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
- How do I update the License after renewal?
- How do I replace existing activation information after capacity expansion?
- Must I activate again after changing editions?
keywords:
- License update
- replace License
- renewal
- capacity expansion
- maintenance window
- update or
- replace a
- License
legacy_ids:
- KB-LICENSE-006
safety_tags:
- license-control
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/license-activation/KB-LICENSE-006-how-to-update-or-replace-license.md
  section: How to update or replace a License?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: how to update or replace a License

## Short answer

After renewal, capacity expansion, or an edition change, first obtain new activation information for the current server. When not activated, select “Activate” under “License Information.” When already activated, select “Edit” under “Server Information,” update the “Activation Code,” and save. The change may require a service restart, so schedule a maintenance window and verify the status, validity period, and limits afterward.

## Prerequisites

This applies to License renewal, traffic or user-count expansion, edition adjustment, or replacement requested by official support in version 8.1.8.7. Without official confirmation, do not use an old file or activation information from another server in the current environment.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **update or replace a License** in the intended deployment, edition, and component.

## Effect

After renewal, capacity expansion, or an edition change, first obtain new activation information for the current server. When not activated, select “Activate” under “License Information.” When already activated, select “Edit” under “Server Information,” update the “Activation Code,” and save. The change may require a service restart, so schedule a maintenance window and verify the status, validity period, and limits afterward.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Under “Device Management > Server Management,” confirm whether the current status is “Not Activated” or “Activated,” and record the visible edition, expiration time, user count, traffic, bandwidth, and other information.
2. Confirm with official sales or technical support that the new entitlement applies to the current product version, edition, and target server.
3. Select an off-peak maintenance window and notify users who may be affected by a restart.
4. If the current status is “Not Activated,” select “Activate” under “License Information,” enter the officially provided activation code, and submit it.
5. If the current status is “Activated,” select “Edit” under “Server Information” on the same page, update the “Activation Code” field, and save. Do not look for the initial activation button under “License Information” to replace an existing License.
6. For offline activation information, enter the offline page, generate an activation request file according to the visible process, deliver it to official technical support, then import the returned activation file and complete activation.
7. If the page prompts for a restart, perform the supported action shown on the page during the maintenance window and wait for the admin center to become available again.
8. Return to “License Information,” confirm that the status is “Activated,” then verify the new expiration time, capacity, user count, and edition one by one.

## Recovery boundary

If old information remains after the update, refresh the page and sign in again before submitting anything again. If new limits do not take effect, the edition is incorrect, or business operations report errors, stop making further changes. Retain non-sensitive before-and-after page records and ask official support to confirm a supported recovery plan.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

An unactivated environment completes initial activation, or an activated environment completes the update through “Edit” under “Server Information.” The validity period and usage limits displayed on the page match the confirmed entitlement. If a restart is required, the status remains normal after the service recovers.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the update requires downtime coordination, restart fails, entitlements are displayed incorrectly, or the previous state must be restored, ask the product administrator to contact official technical support. Provide the product version, before-and-after visible status, edition, error text, and activation method. Do not submit the complete activation code or activation file.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

