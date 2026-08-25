---
id: RSKB-TROUBLE-002
title: Troubleshoot portal login and verification email
product: raysync
components:
- user-portal
- desktop-client
domain: troubleshooting
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
- Why can I not sign in even though the portal address is correct?
- What should I check when a login verification email never arrives?
- Who can help if my account is locked or restricted by network policy?
keywords:
- login failed
- incorrect password
- account locked
- IP restriction
- Why can’t I log in to the Raysync user portal?
- forget password
- reset password
- login email
legacy_ids:
- FAQ-TROUBLE-003
safety_tags:
- credentials
- authorization
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-003 | Why can’t I log in to the Raysync user portal?
  evidence_type: generated-faq
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-005 | Why is the Forget Password option unavailable or not working?
  evidence_type: generated-faq
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-004 | Why didn’t I receive the Raysync login verification email?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Troubleshoot portal login and verification email

## Short answer

Use the exact portal address, account name, password, and authentication method assigned to you. A first login may require a password change. A failure can also result from an incorrect password, an account lockout or inactivity disablement, or an IP access restriction.

## Likely cause

The user guide explicitly shows an "incorrect username or password" result. Security settings can lock an account after consecutive failures, disable it after configured inactivity, or restrict login by IP. LDAP/AD users may need the directory account format configured by the organization.

## What the user can check

Confirm the portal URL and selected authentication method, enter the assigned account name carefully, and complete any first-login password reset. Stop repeated guesses if credentials are uncertain. If an approved **Forget Password** option is present, use it with your login email.

## When to contact an administrator

Contact the administrator if the account may be locked or inactive, the login method is unclear, the network is restricted, or password recovery is unavailable.

## Version differences

The legacy guide documents username/password login, first-login password reset, and local-user email validation. User two-factor authentication is documented from version 8.1.8.6 where supported and enabled. The account format, default authentication method, and required verification remain deployment-specific administrator prerequisites.

## Important notes

Do not share passwords or verification codes.

## Related documented boundaries

- **Why is the Forget Password option unavailable or not working?:** This section covers only failed or unavailable recovery. If **Forget Password** is absent, does not send a message, rejects a delivered code as expired, or fails before a new password can be submitted, record that symptom and escalate it. The normal sequence is covered in the separate forgotten-password recovery guidance.
- **Why didn’t I receive the Raysync login verification email?:** Email verification depends on the Raysync system mailbox configured by the administrator and on the login email stored for your account. A missing message cannot be repaired from the login page if the server mail service or account email is wrong.
