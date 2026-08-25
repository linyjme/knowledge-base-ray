---
id: RSKB-ADMIN-008
title: 'Administrator guide: what is the difference between system email settings and a user’s personal email settings'
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
- How do global SMTP settings differ from a user's personal mail profile?
- Which sender serves system notices versus individual share messages?
- Why can personal mail work while password-recovery mail still fails?
keywords:
- system email
- personal email configuration
- global SMTP
- user email
- share email
- upload invitation
- notification sender
- email information
legacy_ids:
- KB-EMAIL-008
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/email-configuration/KB-EMAIL-008-system-and-user-email-settings.md
  section: What is the difference between system email settings and a user’s personal email settings
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: what is the difference between system email settings and a user’s personal email settings

## Short answer

“Email Settings” in the admin portal provides the global system sending channel. It can be used for system notifications, verification, password recovery, and share or invitation emails when the system email account is selected as the sender. An administrator can also choose “Send Using User-configured Email” for a user. In that case, “Email Configuration” appears in the user portal, and emails for that user’s download shares, upload invitations, and similar actions use the user’s personal sender configuration. A recipient email address in the user profile cannot replace an SMTP sender configuration.

## Prerequisites

This applies in version 8.1.8.7 when an administrator chooses the email sender, or when a user has entered personal email information but system notifications still cannot be sent. The personal “Email Configuration” entry appears in the user portal only when the administrator selects the user-configured email option for that user.



## Effect

Selecting system-configured or user-configured email changes the sender path used by future share and invitation messages in that scope. Saving personal SMTP information changes only that user's configured mailbox; it does not replace the global system sender.

## Confirmation

Confirm the exact sending scenario, target user, intended sender path, authorized mailbox, and whether the change belongs in the admin portal or that user's personal settings.

## Procedure

1. To send system notifications, sign-in email verification, password recovery messages, or share emails from the system account, the administrator enables and verifies the global SMTP configuration under “Email Settings” in the admin portal.
2. Under “Email Sender” in the user settings, the administrator selects either “Send Using System-configured Email” or “Send Using User-configured Email,” as required.
3. After the user-configured option is selected, the user enters and saves personal SMTP information under “Email Configuration” in the user portal. Emails for download shares, upload invitations, and similar actions use that mailbox as the sender.
4. To receive notifications only, verify the personal recipient address in the user profile or business recipient list. This information determines where email is sent; it does not establish the sending connection.
5. Send an actual email and check the sender and recipient to confirm that the expected configuration is used for that scenario.

## Recovery boundary

First determine whether the missing message is a system notification, a user share or invitation, or only a recipient-address issue. Then check the current “Email Sender” selection and the corresponding configuration location. Avoid repeatedly changing the same parameters in several places, which can obscure the actual sending source or recipient problem.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

The administrator-configured system mailbox handles global messages such as system notifications. Share or invitation emails use either the system mailbox or the user-configured mailbox according to the “Email Sender” option selected by the administrator for that user. A personal recipient email address is used only as a destination.

## Escalation

If the user cannot see the personal email configuration, the system still reports that email is not configured, or it is unclear which configuration a message type uses, contact the administrator. Provide the product version, email type, initiating role, send time, and visible page message. Do not provide an email password.
