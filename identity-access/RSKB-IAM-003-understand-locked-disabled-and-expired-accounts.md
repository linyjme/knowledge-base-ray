---
id: RSKB-IAM-003
title: Understand locked, disabled, and expired accounts
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
- Why does my account show locked, disabled, or expired?
- Who can restore access when an administrator has disabled my login?
- What is the difference between a lockout and an expired account?
keywords:
- locked account
- disabled account
- expired account
- administrator
- What does a locked, disabled, or expired account status mean?
- identity access
- Raysync
legacy_ids:
- FAQ-ACCOUNT-006
safety_tags:
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/08-user-account-and-profile.md
  section: FAQ-ACCOUNT-006 | What does a locked, disabled, or expired account status mean?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand locked, disabled, and expired accounts

## Short answer

An administrator can lock or disable a user account. A disabled account cannot log in. An account can also become unavailable when its account-validity period or password-validity period expires, depending on administrator configuration.

There is no documented end-user unlock control. Ask an administrator to check the account status and unlock or re-enable it when appropriate.

## Version differences

The current and earlier account guides document administrator lock/unlock and disabled status. The current guide also documents unavailability after password or account expiration.

## Important notes

Do not assume every login failure means a lock: an incorrect password, IP whitelist, or other authentication requirement can also prevent login. The sources do not provide an end-user diagnostic procedure beyond using correct credentials and contacting the administrator for controlled settings.
