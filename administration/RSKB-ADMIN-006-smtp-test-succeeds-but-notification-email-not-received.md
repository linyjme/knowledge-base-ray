---
id: RSKB-ADMIN-006
title: 'Administrator guide: what to do when the SMTP test succeeds but notification email is not received'
product: raysync
components:
- admin-portal
domain: administration
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- What should I do when the SMTP test succeeds but notification email is not received?
- Why do test emails arrive but system notifications do not?
- Why am I not receiving reminder emails even though the email configuration is valid?
keywords:
- notification email not received
- test email succeeded
- notification rule
- recipient
- spam
- delivery delay
- share email
- system notification
legacy_ids:
- KB-EMAIL-006
safety_tags:
- authorization
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/email-configuration/KB-EMAIL-006-notification-email-not-received.md
  section: What to do when the SMTP test succeeds but notification email is not received
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: what to do when the SMTP test succeeds but notification email is not received

## Short answer

A successful SMTP test only means that the email server accepted that specific test message. It does not mean that every business notification is generated or ultimately reaches the inbox. Continue by checking the relevant notification rule, trigger conditions, recipient email address, spam filtering, and delivery delay.

## Prerequisites

This applies in version 8.1.8.7 when test emails can be sent but a specific share, invitation, system notification, manual notification, email verification, or password recovery email is not received.



## Effect

Enabling a notification point, changing its recipient scope, or correcting a recipient address changes which future events generate email and who receives it. Sending a test email creates one separate diagnostic message.

## Confirmation

Confirm the exact notification point, event conditions, recipient scope, destination address, and approved test event before changing or testing the configuration.

## Procedure

1. Confirm that “Enable Email Notification Service” remains enabled, and send another test email to verify that the basic SMTP configuration is still valid.
2. Check whether the relevant feature or notification rule is enabled and whether the actual event meets its trigger conditions. A rule that is not triggered does not generate an email.
3. Verify the recipient selected in the rule or operation and the email address saved for that user. Rule out a misspelled, empty, or outdated address.
4. Check the inbox, spam folder, quarantine area, and mailbox rules, and confirm that the sender or sender domain is not blocked.
5. Allow the organization’s normal email delivery time and avoid repeatedly triggering the same notification within a short period.
6. Retest with another organization-approved recipient address to determine whether the issue affects only a specific recipient or domain.

## Recovery boundary

Compare the test email and the missing notification by time, recipient address, and spam handling outcome. If only one notification type is missing, first review that feature’s rule and recipients. If all notifications are missing, revalidate the global email settings and sending limits.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

When the rule is enabled, its trigger conditions are met, and the recipient address is valid, the system attempts to submit the notification to the email server. Acceptance by the email server does not guarantee final delivery. Check the inbox, spam folder, quarantine area, or delivery records visible to the email administrator; filtering, bounces, and delivery delays can still affect the final result.

## Escalation

If the rule and recipient are correct but the email still has not arrived after an extended period, ask the application administrator to confirm that the notification was triggered and the email administrator to check delivery or quarantine records for that period. Provide the product version, notification type, trigger time, recipient domain, and visible status. Do not provide a password.
