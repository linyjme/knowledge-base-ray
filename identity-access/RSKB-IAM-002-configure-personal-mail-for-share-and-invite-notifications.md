---
id: RSKB-IAM-002
title: Configure personal mail for share and invite notifications
product: raysync
components:
- user-portal
domain: identity-access
access_level: public
audience:
- end-user
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- When do I need to enter a personal sender mailbox for link notifications?
- Where can I configure the email account that sends my share messages?
- Why does an invite notification need my own SMTP sender settings?
keywords:
- Mail Settings
- SMTP sender
- share notification
- invite notification
- personal mailbox
- system mail service
legacy_ids:
- FAQ-ACCOUNT-004
safety_tags:
- credentials
supersedes: []
superseded_by: []
related_articles:
- RSKB-START-003
source_refs:
- file: raysync-user-faq/08-user-account-and-profile.md
  section: FAQ-ACCOUNT-004 | What are personal mail settings, and when do I need them?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Configure personal mail for share and invite notifications

## Short answer

Open **Personal Center > Mail Settings** to configure the sender email service used for share-download and invite-upload notification messages. This is needed only when an administrator assigns your account to send with a user-configured mailbox.

If the account uses the administrator-configured mailbox, these notification messages use the system mail service and no personal sender configuration is required.

## Notification sender boundary

Personal **Mail Settings** control outgoing share and invite notification mail. They do not configure password recovery, do not replace the account's login email, and do not configure the separate system mail service that sends recovery verification codes.

## Version differences

The current and earlier account guides document the same two sender choices: an administrator-configured system mailbox or an assigned user-configured mailbox.

## Important notes

Treat SMTP passwords as credentials. Do not include them in screenshots, diagnostics, or support messages. If the personal configuration entry is unavailable, ask the administrator which sender option is assigned to the account.
