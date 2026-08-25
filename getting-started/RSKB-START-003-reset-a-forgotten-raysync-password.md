---
id: RSKB-START-003
title: Reset a forgotten Raysync password
product: raysync
components:
- user-portal
domain: getting-started
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
- How can I reset my password when I cannot sign in?
- Why did the recovery code not arrive at my login email?
- What mail service must be available for forgotten-password verification?
keywords:
- forgotten password
- password reset
- verification code
- email
- resend
- system mail
- Why did I not receive a forgotten-password verification code?
- forgot password
legacy_ids:
- FAQ-START-005
safety_tags:
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-006 | Why did I not receive a forgotten-password verification code?
  evidence_type: generated-faq
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-005 | How do I reset a forgotten password?
  evidence_type: generated-faq
- file: raysync-user-faq/08-user-account-and-profile.md
  section: FAQ-ACCOUNT-005 | What must be configured before I can recover a forgotten password?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Reset a forgotten Raysync password

## Short answer

Select **Forget Password** on the login page, enter the login email associated with your account, and use the emailed verification code to set a new password.

## Steps

1. Select **Forget Password**.
2. Enter your login email and select **Next**.
3. Request and enter the verification code, then select **Next**.
4. Enter a valid new password and select **Confirm Reset**.

The password guidance conflicts across the supplied sources. The profile guidance says to use three of four character categories: uppercase letters, lowercase letters, numbers, and special characters. The account-creation guidance requires all four categories, a length of 8–20 characters, no account name, and a password different from the account number. **Because the documented guidance differs, follow the validation shown on your current reset form and any password policy supplied by your administrator.**

## Version differences

The supplied sources do not document a user-visible change to the reset sequence. Across documented versions, password recovery still depends on working system email configured by an administrator.

## Important notes

The verification code expires after 10 minutes. **Resend** becomes available after 60 seconds. Forgotten-password recovery works only when the administrator has configured system email and the account has the correct login email.

Personal **Mail Settings** are not a recovery prerequisite. They configure a sender for share-download and invite-upload notifications; recovery uses the separate system mail service and the account's login email.

## Related documented boundaries

- **Why did I not receive a forgotten-password verification code?:** Raysync can send the forgotten-password verification code only when system email is configured and your login email is registered correctly. Wait until the 60-second resend interval has passed, then select **Resend**. If no code arrives, ask your administrator to verify the account email and the Raysync email configuration.
