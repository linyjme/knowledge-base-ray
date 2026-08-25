---
id: RSKB-LICENSE-002
title: 'License administration: how to activate a License online'
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
- How do I activate a License when the server has internet access?
- What do I need to enter for online activation?
- How do I use the Activate button in the admin center?
keywords:
- online activation
- enter activation code
- Activate button
- activated
- restart prompt
- activate a
- License online
legacy_ids:
- KB-LICENSE-002
safety_tags:
- license-control
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/license-activation/KB-LICENSE-002-how-to-activate-online.md
  section: How to activate a License online?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: how to activate a License online

## Short answer

Under “License Information” in “Device Management > Server Management,” an administrator can select “Activate,” enter an officially provided activation code that applies to the current product, and submit it. After successful activation, the page changes to “Activated” and may prompt you to restart the service through the supported procedure so the change takes effect.

## Prerequisites

This applies to version 8.1.8.7 when the server has the network connectivity required for online activation and you have a valid activation code for the current software version and edition. Product administrator permission is required. Perform the operation during a maintenance window.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **activate a License online** in the intended deployment, edition, and component.

## Effect

Under “License Information” in “Device Management > Server Management,” an administrator can select “Activate,” enter an officially provided activation code that applies to the current product, and submit it. After successful activation, the page changes to “Activated” and may prompt you to restart the service through the supported procedure so the change takes effect.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Confirm that the target server has a stable network connection and that no proxy, firewall, or outbound policy blocks the connection required for online activation.
2. Sign in with an administrator account, go to “Device Management > Server Management,” and select “Activate” under “License Information.”
3. On the “Enter Activation Code” page, paste the officially provided code exactly. Avoid leading or trailing spaces, line breaks, or manual changes.
4. Select “Activate” and wait for the page to return a result. Do not submit repeatedly while the request is being processed.
5. If the page prompts for a restart, use the supported operation shown on the page during the maintenance window.
6. Return to “License Information,” confirm that the status is “Activated,” and verify that the edition, expiration time, and limits are as expected.

## Recovery boundary

For a format error, copy the activation code again from the original delivery information. For a connection failure, check the server network, proxy, and outbound policy. For an invalid, expired, or unsupported-version message, stop repeated attempts and confirm that the code matches the product version and edition. Do not modify activation information through unofficial methods.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

The page displays “Activated,” and the License details are updated with the effective information. If a restart is required, the admin center becomes available again afterward and the status remains “Activated.”

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If network policy cannot be confirmed, the status does not update after activation, the restart cannot be performed safely, or the error persists, contact official technical support. Provide the product version, visible License status, edition, complete error text, and state that this is an online activation scenario. Do not submit the complete activation code.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

