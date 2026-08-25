---
id: RSKB-SECURITY-003
title: Resolve account lockout and weak-password rejection
product: raysync
components:
- user-portal
domain: security
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
- Why was my account locked after several failed password attempts?
- How can I respond when a new password is rejected as too weak?
- Who can unlock or re-enable a Raysync user account?
keywords:
- Password locking, for example, if a user enters an incorrect password for all five attempts, the account will be locked
- account locked
- failed login
- anti-brute-force
- disabled
- password
- Why is my Raysync account locked after failed login attempts?
- weak password
legacy_ids:
- FAQ-SECURITY-007
safety_tags:
- credentials
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-117 | Password locking, for example, if a user enters an incorrect password for all five attempts, the account will be locked
  evidence_type: feature-matrix
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-007 | Why is my Raysync account locked after failed login attempts?
  evidence_type: generated-faq
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-008 | Why does Raysync reject my password as weak?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-118 | Administrator can set weak password dictionary, the password in the dictionary does not allow user to set
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Resolve account lockout and weak-password rejection

## Short answer

The administrator may have enabled the anti-brute-force or login-error limit. The legacy guide allows an account to be locked after a configured number of consecutive incorrect passwords within a configured number of minutes; the threshold can be set from 3 to 30 attempts. The later guide also lists login-error limits and automatic disablement after a configured number of days without login.

## Version differences

Both legacy and later guides document a configurable failed-login limit. The later guide also documents automatic account disablement after a configured period without login. Neither guide describes a self-service unlock action for an end user.

## Important notes

Stop retrying uncertain passwords, because more failed attempts can meet the configured limit. Check that you are using the correct login method and account name. If the account remains locked or has been disabled for inactivity, contact the administrator; the source documentation does not describe an end-user unlock action.

## Related documented boundaries

- **Password locking, for example, if a user enters an incorrect password for all five attempts, the account will be locked:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Why does Raysync reject my password as weak?:** Two different controls can reject a password. First, an administrator can define a weak-password list containing specific values that users are not allowed to set. A password that matches that list is rejected even if it otherwise looks complex.
- **Administrator can set weak password dictionary, the password in the dictionary does not allow user to set:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
