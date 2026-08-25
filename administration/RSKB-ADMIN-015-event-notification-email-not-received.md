---
id: RSKB-ADMIN-015
title: 'Administrator guide: what to do when an event notification email is not received'
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
- Why might configured event email fail to reach its recipient?
- Which notification-rule condition prevents expected messages?
- How can delivery filtering be separated from missed event triggers?
keywords:
- notification not received
- rule status
- event match
- recipient scope
- email configuration
- spam
- delivery delay
- notification troubleshooting
legacy_ids:
- KB-EVENT-007
safety_tags:
- authorization
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/event-notifications/KB-EVENT-007-event-notification-not-received.md
  section: What to do when an event notification email is not received
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: what to do when an event notification email is not received

## Short answer

Troubleshoot in this order: notification point status, whether the event matches, recipient and scope, account email address, system email configuration, spam filtering, and delivery delay. A successful email test or acceptance by the email server confirms only the corresponding sending step; it does not guarantee that the notification reaches the final inbox.

## Prerequisites

This applies in version 8.1.8.7 when a system notification email is not received, is occasionally delayed, or is missing only for some users. If an HTTP callback or program action is missing, check the custom “Event” rule and receiving endpoint instead; the email troubleshooting path does not apply.



## Effect

Enabling a notification point or changing its scope affects which future events send email and which accounts receive it. A test email is a separate real delivery attempt and does not prove that the event rule itself matches.

## Confirmation

Confirm the exact notification point, success or failure condition, role, selected scope, destination account, and approved test event before changing or testing anything.

## Procedure

1. Under “Notifications > System Notifications,” confirm that the exact success/failure, user/administrator, or sender/recipient notification point is enabled.
2. Confirm that the actual event meets the notification point’s conditions. Its status, transfer direction, event role, storage threshold, and conditions such as “Do not send email notifications for instant-transfer files” must match.
3. Open the notification point settings and confirm that the relevant transfer users, recipient administrators, or file library scope includes this event. Then verify the creator, sender, or recipient involved in the event.
4. Confirm that the destination account has a valid email address. Under “Notifications > Email Settings,” confirm that “Enable Email Notification Service” is selected and send a test email.
5. Check spam, quarantine, mailbox rules, allowlists, and bounces. Allow the organization’s normal delivery time and avoid repeatedly triggering the event.
6. Retest using another approved mailbox within the scope to distinguish a rule, account, or email-domain issue.

## Recovery boundary

Compare the recipient address, trigger time, and filtering result between the test email and business notification. If only one notification point is missing, prioritize its event conditions and scope. If every system email is missing, prioritize the global email configuration.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

When the rule is enabled, the event matches, the scope is correct, the recipient email is valid, and the email service is available, the system attempts to submit the notification email. Final delivery may still be affected by provider rejection, filtering, rate limits, or delays.

## Escalation

If all items above are correct but the email still has not arrived after an extended period, ask the application administrator to confirm the event match and sending status, and ask the email administrator to check delivery or quarantine results for that period. Provide the version, notification point, trigger time, recipient domain, and page status. Do not provide a password.
