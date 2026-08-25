---
id: RSKB-IAM-007
title: 'Identity administration: which user authentication and integration methods are supported in 8.1.8.7'
product: raysync
components:
- admin-portal
domain: identity-access
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
- Which user sign-in methods does the system support?
- Can LDAP, AD, or OIDC be integrated?
- Which authentication options are available for user integration?
keywords:
- user integration
- sign-in authentication
- LDAP/AD domain
- OpenID Connect
- external authentication
- which user
- authentication and
- integration methods
legacy_ids:
- KB-USER-001
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/user-integration/KB-USER-001-supported-integration-methods.md
  section: Which user authentication and integration methods are supported in 8.1.8.7?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identity administration: which user authentication and integration methods are supported in 8.1.8.7

## Short answer

The sign-in authentication page in version 8.1.8.7 displays Local User, LDAP/AD Domain, Email, System, External HTTP Authentication, and OpenID Connect. Actual availability depends on the product edition, License, deployment environment, and whether an administrator completed the configuration. Follow the current admin console and organizational solution.

## Prerequisites

This applies to administrators responsible for unified identity, directory integration, or sign-in entry planning. LDAP/AD Domain can integrate directory accounts, while OpenID Connect can connect a compatible identity provider. Administrators should select other methods according to the organization’s existing identity system.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Effect

Enabling an authentication method exposes that sign-in path to its intended users, and choosing a default changes the entry offered by default. Incorrect identity-provider, credential, role, or default-method settings can prevent sign-in or grant an unintended initial role.

## Confirmation

Confirm the exact authentication method, identity system owner, credential handling, intended users, default role, fallback administrator access, and controlled test account before enabling it or making it the default.

## Procedure

1. In the admin console, go to “User Integration” and open “Sign-in Authentication.”
2. Review the authentication methods listed on the page and their enabled status. An unavailable item usually means that current edition, License, or environment prerequisites are not met.
3. Complete configuration and security testing for the selected method before enabling it.
4. Configure authorization settings such as the default role for integrated users and select an appropriate default authentication method.
5. Verify sign-in, sign-out, and basic access scope with a non-privileged test account before notifying production users.

## Recovery boundary

Confirm the product version and License status, check whether the authentication method is enabled and saved, and verify that the external identity service is available. Do not assume the environment is ready merely because an option appears on the page.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

Configured and enabled authentication methods appear in Sign-in Authentication settings. Users can initiate authentication from the corresponding entry and receive administrator-assigned product permissions after successful authentication.

## Escalation

If an authentication option is hidden or cannot be enabled, or the organization does not know which method to select, ask an administrator to confirm the version, License, deployment conditions, and identity-governance requirements. Provide only the product version, authentication method name, and customer-visible status. The organization must always protect account credentials.
