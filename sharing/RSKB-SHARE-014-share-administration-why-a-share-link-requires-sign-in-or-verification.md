---
id: RSKB-SHARE-014
title: 'Share administration: why a share link requires sign-in or verification'
product: raysync
components:
- admin-portal
- user-portal
domain: sharing
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
- Why does a share link require sign-in?
- Isn’t an external link public?
- Why must I enter an access password?
keywords:
- sign-in requirement
- email verification
- access password
- Internal Members
- Specified Email Addresses
- why a
- share link
- requires sign-in
legacy_ids:
- KB-SHARE-006
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/share-links/KB-SHARE-006-why-share-link-requires-sign-in.md
  section: Why a share link requires sign-in or verification
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Share administration: why a share link requires sign-in or verification

## Short answer

Sign-in, email verification code, or access password is normal behavior required by the creator’s selected share scope and administrator security settings. It does not indicate a broken link. Anyone, Internal Members, and Specified Email Addresses may use different verification methods; the page shows the verification required for the current link.

## Scope and evidence

This applies to recipients who see an account sign-in, email verification, or access-password page after opening a download share or upload invitation in version 8.1.8.7.

Changing whether a link can be used does not delete or remove the shared files or uploaded content. Link access and content deletion are separate controls and require separate authorization.

## Documented details

1. Confirm that the link comes from a trusted creator and which identity you should use. Do not give your sign-in information to someone else to enter.
2. For Internal Members, sign in with an invited member account. If the creator selected only certain members, another valid account may still lack permission.
3. For Specified Email Addresses, use the invited address and receive and enter the verification code as shown. Check the spam folder, but do not forward the code to unrelated people.
4. When the page requires an access password, use the password delivered by the creator through a secure channel. If it is invalid, ask the creator to verify it instead of guessing repeatedly.
5. If the creator believes verification should not be required, the creator should check the share/invitation scope in link details and ask the administrator to verify security settings such as external-person email verification.

## Interpretation and recovery boundary

Verify the email spelling, verification-code validity, account scope, and link status. Close the old page and open the original link again. If the verification email does not arrive, first confirm that email service works and ask the creator to resend the address by copying the link.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

After identity, email, or password verification succeeds and other access conditions are met, the page displays the permitted files and actions. Access remains denied when the scope or policy is not satisfied.

## Escalation

If the invited identity is correct but access remains denied, no verification emails are delivered, the page uses an unexpected sign-in method, or the creator cannot view security settings, ask an administrator to check access scope, identity method, and email-verification policy. Provide the version, access time, identity type, and visible message. Do not provide a password or verification code.

