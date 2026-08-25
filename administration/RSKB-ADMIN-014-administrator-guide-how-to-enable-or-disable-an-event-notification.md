---
id: RSKB-ADMIN-014
title: 'Administrator guide: how to enable or disable an event notification'
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
- How do I enable or disable an event notification?
- How do I re-enable an event rule that is shown as disabled?
- What should I do if I temporarily do not want to receive system notifications?
keywords:
- enable notification
- disable notification
- disabled rule
- notification switch
- retain configuration
- future event
- enable or
- disable an
legacy_ids:
- KB-EVENT-006
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/event-notifications/KB-EVENT-006-how-to-enable-or-disable-notification.md
  section: How to enable or disable an event notification
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to enable or disable an event notification

## Short answer

Change the status of a custom event rule with “Enable Event” under “Edit.” For a system email notification, use the switch for the corresponding notification point. Disabling is not the same as deleting: the configuration is retained and can be enabled again later. A status change affects only subsequent matching events and does not recall notification actions that were already initiated.

## Prerequisites

This applies to administrators who need to pause or resume a custom event rule or system email notification point in version 8.1.8.7. Even when a system email notification is enabled, it still depends on a valid recipient address and a working email notification service.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **enable or disable an event notification** in the intended deployment, edition, and component.

## Effect

Change the status of a custom event rule with “Enable Event” under “Edit.” For a system email notification, use the switch for the corresponding notification point. Disabling is not the same as deleting: the configuration is retained and can be enabled again later. A status change affects only subsequent matching events and does not recall notification actions that were already initiated.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Custom event: Go to “System Configuration > More Settings > Event Settings,” locate the rule, and select “Edit.”
2. Select or clear “Enable Event,” save, and verify that the list shows the status as “Enabled” or “Disabled.”
3. System email notification: Go to “System Configuration > Notifications > System Notifications,” locate the exact notification point, and change its email switch.
4. Before resuming notifications, verify that the event type, receiving scope, receiving endpoint, and email settings are still valid.
5. Verify the result with an event that occurs after the save. Do not use a historical event from before the switch change to judge the result.

## Recovery boundary

Refresh the page to confirm that the status was saved, and verify that you did not change a similar but different success, failure, administrator, or user notification point. If notifications continue, check for another rule of the same type or another role-specific notification point.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

After the rule is enabled, subsequent matching events attempt the notification according to the other configured conditions. After it is disabled, the rule or notification point no longer handles subsequent matching events, but its settings are retained.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the switch is not visible, saving fails, the status changes back automatically, or the notification source cannot be identified after disabling, contact an administrator. Provide the rule or notification point name, operation time, page status, and subsequent event time.

