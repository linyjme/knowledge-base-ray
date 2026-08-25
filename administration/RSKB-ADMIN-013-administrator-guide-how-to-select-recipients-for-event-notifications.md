---
id: RSKB-ADMIN-013
title: 'Administrator guide: how to select recipients for event notifications'
product: raysync
components:
- admin-portal
domain: administration
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
- How do I select recipients for event notifications?
- Who can receive system notification emails?
- Where do I select recipient administrators and transfer users?
keywords:
- recipient
- recipient administrator
- transfer user
- file library
- user email
- permission visibility
- select recipients
- for event
legacy_ids:
- KB-EVENT-005
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/event-notifications/KB-EVENT-005-how-to-select-recipients.md
  section: How to select recipients for event notifications
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to select recipients for event notifications

## Short answer

Under “Notifications > System Notifications,” select the settings button beside the target notification point, then choose transfer users, recipient administrators, or file libraries as displayed on the page. Recipients differ by the role involved in an event: they may be the creator, sender, recipient, space administrator, or a selected administrator. Not every notification point provides manual recipient selection.

## Prerequisites

This applies to system email notifications in version 8.1.8.7. You need permission to configure system notifications, and the notification service under “Email Settings” must be enabled. Each actual recipient account must have a valid email address. Some labels define the trigger scope rather than additional recipients. For example, “Transfer Users” in an administrator notification limits which users’ transfers trigger the notification.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **select recipients for event notifications** in the intended deployment, edition, and component.

## Effect

Under “Notifications > System Notifications,” select the settings button beside the target notification point, then choose transfer users, recipient administrators, or file libraries as displayed on the page. Recipients differ by the role involved in an event: they may be the creator, sender, recipient, space administrator, or a selected administrator. Not every notification point provides manual recipient selection.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Go to “System Configuration > Notifications > System Notifications” and locate the exact notification point.
2. If the row has a settings button, open it and select transfer users, recipient administrators, or file libraries according to the visible labels. Select only the scope required by the business.
3. Verify that the email addresses of the relevant user and administrator accounts are not empty, misspelled, or disabled.
4. Review the email template and “More Settings” if needed, save, and then enable the notification point.
5. Test with one account inside the selected scope and one outside it to confirm that the trigger scope and recipient result are as expected.

## Recovery boundary

Confirm that the selected objects match the creator, sender, recipient, space, or file library in the actual event, and check the account email and notification switch. Acceptance by the email server does not guarantee final delivery; filtering and delays must also be checked.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

When a subsequent event meets the notification point’s conditions and the object is within the configured scope, the system attempts to submit email to the valid address associated with the event. A notification point without a settings button determines recipients from the event roles defined on the page.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the target user, administrator, or file library is not visible, the settings button is unavailable, you cannot modify the account email, or the trigger scope is unclear, contact an administrator with the required permissions. Provide the notification point, account or file library name, and trigger time. Do not provide an email password.

