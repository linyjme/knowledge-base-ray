---
id: RSKB-ADMIN-012
title: 'Administrator guide: how to edit or delete an event notification rule'
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
- How do I edit or delete an event notification rule?
- Where can I edit an incorrectly selected event type?
- How do I delete an event callback that is no longer used?
keywords:
- edit event
- delete event
- bulk delete
- future notifications
- event list
- cannot recall
- edit or
- delete an
legacy_ids:
- KB-EVENT-004
safety_tags:
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/event-notifications/KB-EVENT-004-how-to-edit-or-delete-event-notification.md
  section: How to edit or delete an event notification rule
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to edit or delete an event notification rule

## Short answer

Use “Edit” or “Delete” in the rule list under “System Configuration > More Settings > Event Settings.” You can also select multiple rules and delete them in bulk. Editing or deleting affects only matching events that occur after the change is saved. It does not recall a program execution or callback request that was already initiated, and it cannot change the historical event. Preset email notifications are not part of this list; disable the corresponding notification point separately under “System Configuration > Notifications > System Notifications.”

## Prerequisites

This applies to custom “Event” rules in version 8.1.8.7. Preset “System Notifications” cannot be added or deleted. You can only modify their visible recipient scope, email template, or advanced settings, or disable a notification point with its switch.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **edit or delete an event notification rule** in the intended deployment, edition, and component.

## Effect

Use “Edit” or “Delete” in the rule list under “System Configuration > More Settings > Event Settings.” You can also select multiple rules and delete them in bulk. Editing or deleting affects only matching events that occur after the change is saved. It does not recall a program execution or callback request that was already initiated, and it cannot change the historical event. Preset email notifications are not part of this list; disable the corresponding notification point separately under “System Configuration > Notifications > System Notifications.”

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Identify the target in the event list by its name, type, action, and status so that you do not edit or delete a similarly named rule.
2. To modify it, select “Edit,” verify the event type, receiving endpoint, timeout, and “Enable Event” status, then save.
3. To delete it, select “Delete” for one rule, or select multiple rules and use “Delete” above the list. Verify the scope again in the confirmation dialog.
4. If you only want to pause future triggers temporarily, edit the rule and clear “Enable Event” so that the configuration is retained for later use.
5. After saving or deleting, refresh the list and verify the result with a new event.

## Recovery boundary

If the list still shows old information, refresh and check again. If the outcome does not change after editing, confirm that you are observing a new event that occurred after the save and rule out another enabled rule of the same type triggering at the same time.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

The modified rule handles matching events using the new settings after the save. A deleted rule disappears from the list and no longer handles subsequent matching events. Notification actions that already started or completed are not recalled.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the Edit or Delete action is unavailable, a rule was deleted by mistake, you cannot determine whether overlapping rules exist, or the receiving endpoint continues to receive actions, contact an administrator. Provide the rule name, operation time, saved status, and time of a subsequent event.

