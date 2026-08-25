---
id: RSKB-ADMIN-001
title: 'Administrator guide: how to configure an SMTP email server'
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
- How do I configure an SMTP email server?
- Where can I configure the system email account?
- How do I enable the email notification service?
keywords:
- SMTP
- email settings
- email server
- email notification service
- SMTP authentication
- save email configuration
- configure an
- SMTP email
legacy_ids:
- KB-EMAIL-001
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/email-configuration/KB-EMAIL-001-how-to-configure-smtp.md
  section: How to configure an SMTP email server
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to configure an SMTP email server

## Short answer

An administrator can enable the email notification service under “Email Settings” in the admin portal, enter the SMTP information provided by the email service provider, and save the configuration. After the system successfully connects and completes the required authentication, it saves the configuration and displays a success message.

## Prerequisites

This applies to administrators who need to send share, invitation, system notification, manual notification, email verification, or password recovery emails in version 8.1.8.7. Before you begin, confirm the SMTP address, port, encryption method, and whether the account is permitted to send email through SMTP with the email service provider.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **configure an SMTP email server** in the intended deployment, edition, and component.

## Effect

An administrator can enable the email notification service under “Email Settings” in the admin portal, enter the SMTP information provided by the email service provider, and save the configuration. After the system successfully connects and completes the required authentication, it saves the configuration and displays a success message.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Sign in to the admin portal with an administrator account and open “Email Settings.”
2. Select “Enable Email Notification Service.”
3. Enter the “Sender Name” and select the “Email Type.” Even when you select a preset type, verify the automatically populated SMTP address, port, and encryption method against the provider’s current requirements.
4. Select “SMTP Authentication.” When using “Login,” enter the “SMTP Email” and “SMTP Password.” When using “Open,” you must still enter the SMTP email address, but a password is not required and the email server must explicitly allow this method.
5. Enter the “SMTP Address” and “SMTP Port,” then select the matching “Encryption Method.”
6. Click “Save.”

## Recovery boundary

Confirm that all required fields are complete, then verify the SMTP address, port, encryption method, account, and password in order. Do not disable encryption to work around a connection problem; use a combination explicitly supported by the email service provider. After saving, use the test email procedure to verify delivery.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

The page displays a success message. When you reopen Email Settings, the saved non-sensitive configuration is displayed. While the service is enabled, eligible email features use this system email configuration to send messages.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the page continues to report connection, authentication, or sending failures, contact the email administrator to confirm the account’s SMTP permissions and sender policies. Provide technical support with the product version, email type, time of the operation, and the visible error message only. Do not provide the password.

