---
id: RSKB-SHARE-013
title: Why is a share link locked or restricted to another device?
product: raysync
components:
- admin-portal
- user-portal
domain: sharing
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
- Why can’t I open the share link?
- What should I do when the link does not exist?
- Can an expired external link still be used?
keywords:
- link does not exist
- expired
- disabled
- link locked
- access restricted
- why is
- a share
- or restricted
legacy_ids:
- KB-SHARE-005
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/share-links/KB-SHARE-005-share-link-invalid-expired-or-locked.md
  section: What to do when a share link is invalid, expired, disabled, or locked
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Why is a share link locked or restricted to another device?

## Short answer

First distinguish a nonexistent, expired, disabled, locked, or policy-blocked link. “Link Locked” differs from “Device Bound”: locking is a separate security status that an administrator or technical support must check, while device binding only restricts access to an approved device and must not be handled as locking.

## Prerequisites

This applies in version 8.1.8.7 when opening a download share or upload invitation shows nonexistent, expired, disabled, locked, insufficient permission, expired sign-in, or device-bound messages, or when upload/download actions are no longer available.

Changing whether a link can be used does not delete or remove the shared files or uploaded content. Link access and content deletion are separate controls and require separate authorization.

## Effect

Re-enabling a disabled link restores access to the same share policy; recreating a missing or deleted record creates a new link. Device unbinding changes only the approved device association and does not unlock the link, extend expiration, or delete shared content.

## Confirmation

Confirm the exact link record, creator or administrator authority, current In Use, Expired, Disabled, missing, or device-bound state, intended access scope, and whether re-enable, recreate, or visible device unbinding is appropriate.

## Procedure

1. Copy the complete link again from the creator’s original message to avoid missing characters or using a replaced old link. Do not modify the link yourself.
2. Ask the creator to verify in the Share Links list that the record exists and whether its status is “In Use,” “Expired,” or “Disabled.”
3. For “Expired,” ask the creator to generate a new policy-compliant link. “Disabled” means the share was disabled or canceled and can be re-enabled by an authorized person. A missing or deleted record must be recreated.
4. If the page explicitly shows “Link Locked,” stop repeated attempts and retain the visible message, time, and link status for secure review by an administrator or technical support. A customer cannot clear this status independently.
5. If the page says a device is bound or access is limited to a specific device, use the originally approved device or ask an administrator whether visible Device Unbinding is allowed. Device unbinding cannot unlock a link and does not change expiration, disabled, or policy-blocked status.
6. If access is denied, confirm that you belong to the Internal Members or Specified Email Addresses scope and complete sign-in, email, or password verification as shown.

## Recovery boundary

Open the original link again in a supported browser or private window, confirm that system time and network are normal, and record the complete visible message. Do not repeatedly guess passwords, modify the link, or use an unauthorized identity.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

After the exact status is identified, nonexistent, expired, and disabled links can be handled by resending, recreating, or compliant re-enabling. Device binding is handled with an approved device or visible unbinding operation. An administrator or technical support determines the next step for link locking and policy blocking.

## Escalation

Contact an administrator or technical support when the page shows “Link Locked,” the list shows “In Use” but all compliant recipients are rejected, Device Unbinding is unavailable, access scope conflicts with the message, or the policy-block reason is unclear. Provide the product version, time, link status, access scope, and a screenshot of the message, with passwords and personal sensitive information redacted.
