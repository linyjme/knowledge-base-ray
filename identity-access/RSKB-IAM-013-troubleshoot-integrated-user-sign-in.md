---
id: RSKB-IAM-013
title: 'Identity administration: how to troubleshoot an integrated user who cannot sign in'
product: raysync
components:
- admin-portal
domain: identity-access
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Why can’t an LDAP user sign in?
- What should I do if an OIDC user cannot enter the system?
- How do I handle a third-party account reported as unavailable?
keywords:
- sign-in failure
- account status
- account mapping
- identity provider
- visible error
- troubleshoot an
- integrated user
- who cannot
legacy_ids:
- KB-USER-007
safety_tags:
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/user-integration/KB-USER-007-integrated-user-cannot-sign-in.md
  section: How to troubleshoot an integrated user who cannot sign in?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identity administration: how to troubleshoot an integrated user who cannot sign in

## Short answer

First confirm that the user selected the correct authentication method, then check account status, account mapping, identity-provider status, time, and network in order. Retain the error displayed on the sign-in page and its time so administrators can identify the failing stage.

## Scope and evidence

This applies when LDAP/AD Domain, Email, System, External HTTP Authentication, or OpenID Connect users cannot sign in to version 8.1.8.7. Do not collect or forward user passwords, verification codes, client credentials, or tokens while troubleshooting.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

1. Confirm that the method selected on the sign-in page matches the account source. The administrator checks that the method is enabled and remains the intended entry.
2. Check that the user account exists at the external identity service, is enabled, unlocked, and unexpired, and that the corresponding product account is not disabled or locked.
3. Verify that the account, email, or organization identifier used to match the user agrees with current configuration, especially after recent renames, domain changes, or duplicate accounts.
4. Use an administrator-provided low-privilege test account to confirm whether the identity provider or directory service is generally available. If several users fail at once, prioritize service-outage handling.
5. Check that time is accurate on the user device, product server, and identity service, that the browser can access the organization-approved sign-in address, and that network policy does not block redirects.
6. Record the visible page error, failure time, authentication method, impact scope, and last successful time, then hand them to the appropriate administrator.

## Interpretation and recovery boundary

Clear the current sign-in-page session and retry once from the correct entry to avoid interference between identity-provider sessions. If it still fails, stop repeated attempts that may lock the account and continue following existing organizational authentication security requirements.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

When account status, mapping, and the external service are normal, the user can authenticate and return to the product. If authentication succeeds but spaces or features are missing, troubleshoot authorization instead of continuing to change sign-in configuration.

## Escalation

If several users fail, account mapping is unclear, the page reports a redirect or service error, the account is locked, or time or network must be adjusted, contact the product and identity-service administrators. Redact account, email, and organization information before providing a non-sensitive screenshot.

