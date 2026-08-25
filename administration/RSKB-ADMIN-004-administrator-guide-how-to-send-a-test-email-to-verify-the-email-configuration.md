---
id: RSKB-ADMIN-004
title: 'Administrator guide: how to send a test email to verify the email configuration'
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
- Where is the SMTP delivery test available in Email Settings?
- How can outgoing mail settings be checked from the admin portal?
- What proves that the configured mailbox accepts a test message?
keywords:
- test email
- test mailbox
- send test email
- SMTP test
- email configuration verification
- save
- inbox
- delivery acceptance
legacy_ids:
- KB-EMAIL-004
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/email-configuration/KB-EMAIL-004-how-to-test-email-configuration.md
  section: How to send a test email to verify the email configuration
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to send a test email to verify the email configuration

## Short answer

In “Email Settings” in the admin portal, enable the email notification service and complete the SMTP configuration. Enter a valid recipient address under “Test Email,” then click “Send Test Email.” A successful test displays a success message, and the destination mailbox should receive an email whose subject and body identify it as a test message.

## Prerequisites

This applies when an administrator verifies the connection and sending capability of the current form after the initial setup, after changing SMTP parameters, or while troubleshooting email issues in version 8.1.8.7. A test does not save the configuration; after the test succeeds, you must still click “Save” to retain the settings.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **send a test email to verify the email configuration** in the intended deployment, edition, and component.

## Effect

In “Email Settings” in the admin portal, enable the email notification service and complete the SMTP configuration. Enter a valid recipient address under “Test Email,” then click “Send Test Email.” A successful test displays a success message, and the destination mailbox should receive an email whose subject and body identify it as a test message.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Confirm that “Enable Email Notification Service” is selected and complete the sender, email type, SMTP authentication, account, required password, address, port, and encryption method.
2. Under “Test Email,” enter the complete address of a mailbox that can receive messages and is approved for testing.
3. Click “Send Test Email” and wait for the page to return a result. Do not click repeatedly while the test is running.
4. After the page reports success, check the destination inbox, spam folder, and quarantine area.
5. After verification, click “Save,” then refresh the page to confirm that the configuration remains available.

## Recovery boundary

If the page reports an error immediately, follow the test-email failure procedure to check the SMTP parameters. If the page reports success but no message arrives, verify the test address, allow a reasonable delivery time, and check spam, quarantine, and recipient rules.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

The page reports a successful test and the destination mailbox receives the test email. Page-level success means that the email server accepted this send request; final inbox delivery may still be affected by recipient filtering and delivery delays.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If repeated tests fail, or no delivery record appears long after the page reports success, contact the email administrator. Provide the test time, recipient domain, page result, and a visible error summary. Do not provide the SMTP password.
