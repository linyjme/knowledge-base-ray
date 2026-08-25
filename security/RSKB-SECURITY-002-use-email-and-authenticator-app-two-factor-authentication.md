---
id: RSKB-SECURITY-002
title: Use email and authenticator-app two-factor authentication
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
- How do I complete login with an emailed two-factor code?
- Can I use an Authenticator App for Raysync user verification?
- Why does my account request a second factor after the password?
keywords:
- email code
- 2FA
- MFA
- login
- verification
- Why am I asked for an email verification code when I log in?
- Authenticator App
- Google Authenticator
legacy_ids:
- FAQ-SECURITY-004
safety_tags:
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-004 | Why am I asked for an email verification code when I log in?
  evidence_type: generated-faq
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-005 | Can I use an Authenticator App for Raysync two-factor authentication?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-120 | Users can log in without email verification
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-119 | Support 2FA login verification for both users and administrators(Email,Authenticator App)
  evidence_type: feature-matrix
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-006 | What should I do if I lose or replace my Authenticator App device?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Use email and authenticator-app two-factor authentication

## Short answer

Your administrator has enabled email verification. Enter your password and the verification code delivered to the login email address. The legacy guide documents password-plus-email validation for local users. For deployments that support the later user multi-factor feature, the current guide allows email verification for user login and modification of user information, with IP-based verification scope.

## Version differences

The legacy guide documents password-plus-email validation for local users and requires a configured system mailbox. The current guide family describes both email and Authenticator App methods, but guide-family placement does not establish when each option became available. The release list places administrator two-factor authentication at 8.1.8.3 and user two-factor authentication at 8.1.8.6. Version 8.1.8.6 therefore extends supported two-factor authentication to users; it does not introduce administrator two-factor authentication for the first time.

## Important notes

Code delivery depends on the administrator’s system mailbox configuration. Confirm that your Raysync profile has the expected login email and check spam or quarantine folders. If no message arrives, an administrator must verify the configured mailbox and your account email; the end-user guides do not provide server-mail repair steps.

## Related documented boundaries

- **Can I use an Authenticator App for Raysync two-factor authentication?:** Yes, when your administrator enables the Authenticator App method. Raysync documents compatibility with authenticator applications such as Google Authenticator and Microsoft Authenticator for user login and modification of user information. Follow the enrollment and code prompts shown by your Raysync service.
- **Users can log in without email verification:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Support 2FA login verification for both users and administrators(Email,Authenticator App):** SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported The source records 6.4.8.0; 8.1.8.6(administrator, add Authenticator App) as an appearance or change milestone, not as proof of the onset of support.
- **What should I do if I lose or replace my Authenticator App device?:** Contact your Raysync administrator and request **Reset authenticator** for your user account. Raysync documents this administrative reset specifically for a user who loses the authenticator or changes devices. The end-user documentation does not provide a self-service bypass.
