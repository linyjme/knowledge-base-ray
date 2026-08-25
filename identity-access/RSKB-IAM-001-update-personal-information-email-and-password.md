---
id: RSKB-IAM-001
title: Update personal information email and password
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
- Where can I update my real name and login email?
- How do I change a known password while I am signed in?
- Why is forgotten-password recovery separate from Personal Center changes?
keywords:
- personal information
- real name
- Personal Center
- How do I view and update my personal information?
- login email
- User Message
- password recovery
- How do I update the email address used for login and recovery?
legacy_ids:
- FAQ-ACCOUNT-001
safety_tags:
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/08-user-account-and-profile.md
  section: FAQ-ACCOUNT-001 | How do I view and update my personal information?
  evidence_type: generated-faq
- file: raysync-user-faq/08-user-account-and-profile.md
  section: FAQ-ACCOUNT-003 | How do I update the email address used for login and recovery?
  evidence_type: generated-faq
- file: raysync-user-faq/08-user-account-and-profile.md
  section: FAQ-ACCOUNT-002 | How do I change my Raysync password while signed in?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Update personal information email and password

## Short answer

In the user portal, select your user name in the upper-right corner, then open **Personal Center**. Open **User Message** to view and edit the personal fields documented for end users, including your real name and login email.

Your account number is different from these editable profile fields. The administrator-side user documentation states that the account number cannot be modified after the account is created.

## Password boundary

Changing a password while signed in uses the current-password profile flow. Forgotten-password recovery is a separate mail-verification flow and depends on an accessible login email and configured system mail.

## Version differences

The cited sources do not document a user-visible version difference for these **Personal Center** steps.

## Important notes

Some account properties—permissions, home directory, role, status, validity, and transfer settings—are administrator-controlled and are not editable from Personal Center.

## Related documented boundaries

- **How do I update the email address used for login and recovery?:** Open your user-name menu, select **Personal Center**, and open **User Message**. Edit the login email and save it. Raysync supports email login, and the forgot-password workflow sends its verification code to the account's login email.
- **How do I change my Raysync password while signed in?:** Select your user name in the upper-right corner, open **Personal Center**, and select **Update Password**. Enter the required current and new password information shown by the form, then save the change. Use the new password the next time you log in.
