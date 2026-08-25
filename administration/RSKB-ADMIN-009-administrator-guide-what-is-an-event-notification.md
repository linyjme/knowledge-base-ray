---
id: RSKB-ADMIN-009
title: 'Administrator guide: what is an event notification'
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
- What is an event notification?
- What does the system do after an event is triggered?
- How are event rules related to system email notifications?
keywords:
- event notification
- trigger condition
- event rule
- recipient
- system notification
- email notification
- what is
- an event
legacy_ids:
- RS-FEAT-194
- KB-EVENT-001
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-194 | Notification of file events
  evidence_type: feature-matrix
- file: knowledge-base/event-notifications/KB-EVENT-001-what-is-event-notification.md
  section: What is an event notification
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: what is an event notification

## Short answer

Event notifications associate visible product events with subsequent actions. After an event meets its trigger conditions, the system checks enabled rules and attempts to perform the configured notification action for the rule’s recipient. In version 8.1.8.7, recipients for custom “Event” rules are executable programs or HTTP callback services. “System Notifications,” by contrast, use preset notification points to attempt to send email to users or administrators within the configured scope. These are separate settings.

## Prerequisites

This applies to administrators who need to understand how custom event callbacks or system email notifications work in version 8.1.8.7. Availability of the custom event entry depends on the product version and permissions. System email notifications also require a working notification service under “Email Settings” and valid recipient email addresses.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

## Effect

Saving and enabling a custom event can execute a configured program or HTTP callback when a future event matches. Enabling a system notification can send email to the selected user, administrator, library, creator, sender, or recipient scope.

## Confirmation

Confirm the exact event type, action, receiving endpoint or recipient scope, enabled state, and a controlled verification event before saving.

## Procedure

1. First determine whether the event should be sent to a program or HTTP service, or whether a system notification email should be sent to people.
2. For a custom event, select the exact event type, notification action, and receiving endpoint, then decide whether to enable it immediately.
3. For a system email notification, select the preset notification point and verify the applicable transfer users, recipient administrators, file libraries, or the creator, sender, and recipient involved in the event.
4. After saving, verify the configuration with an identifiable test or real operation. Do not treat “saved successfully” as proof that the receiving endpoint processed the request or that email was delivered.

## Feature-matrix evidence

- Knowledge base ID: RS-FEAT-194
- Original source text: Notification of file events
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 194

## Recovery boundary

Check the rule status, actual event type, recipient, and action configuration in order. For email notifications, also check the email service, recipient address, spam filtering, and delivery delay. For callbacks, ask the receiving endpoint owner to confirm whether the request was received and processed successfully.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

When a subsequent event matches an enabled rule, the system attempts to perform the configured action. Results differ when the event does not match, the rule is disabled, the receiving scope excludes the relevant object, or email conditions are not met.

## Escalation

If the entry is not visible, you lack permission to modify it, the product version cannot be confirmed, or testing repeatedly fails, contact an administrator or technical support. Provide the rule name, event type, trigger time, page status, and a redacted visible message. Do not provide passwords, complete credentials, or sensitive notification content.
