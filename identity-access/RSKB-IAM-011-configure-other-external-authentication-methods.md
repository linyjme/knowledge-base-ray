---
id: RSKB-IAM-011
title: 'Identity administration: how to select and configure other external authentication methods'
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
- Which external identity providers complement LDAP or OIDC?
- When is HTTP authentication appropriate for user sign-in?
- What prerequisites apply to email-based or operating-system authentication?
keywords:
- external HTTP authentication
- email authentication
- System
- permission ownership
- third-party authentication
- authentication selection
- external identity configuration
- external authentication
legacy_ids:
- KB-USER-005
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/user-integration/KB-USER-005-how-to-configure-external-authentication.md
  section: How to select and configure other external authentication methods?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identity administration: how to select and configure other external authentication methods

## Short answer

Besides LDAP/AD Domain and OpenID Connect, the version 8.1.8.7 Sign-in Authentication page also displays Email, System, and External HTTP Authentication. They serve different existing identity environments. Availability depends on the edition, License, deployment conditions, and authentication services already provided by the organization.

## Prerequisites

Email authentication suits organizations that can reliably authenticate users through email. System applies only when the deployment environment supports system accounts governed by administrators. External HTTP Authentication suits an organization with a supported external authentication service. Before selecting one, clarify the account source, ownership of sign-in credentials, and whether permissions are managed by the product or external service.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **select and configure other external authentication methods** in the intended deployment, edition, and component.

## Effect

Besides LDAP/AD Domain and OpenID Connect, the version 8.1.8.7 Sign-in Authentication page also displays Email, System, and External HTTP Authentication. They serve different existing identity environments. Availability depends on the edition, License, deployment conditions, and authentication services already provided by the organization.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Go to “User Integration > Sign-in Authentication” and confirm that the target method can be enabled in the current environment.
2. For Email authentication, configure the authentication name and email service information as shown and complete the page test first. Users also need valid email information.
3. For System authentication, set the display name as shown and ask the system administrator to confirm account availability and security policy in the deployment environment.
4. For External HTTP Authentication, enter the name, authentication type, and authentication service URL supplied by the organization administrator. If product-controlled permissions are selected, configure the user synchronization scope and default role as shown.
5. Verify sign-in, whether the account appears in the account list, permission ownership, and sign-out behavior with a regular test account before enabling the method or making it default.

## Recovery boundary

Confirm the method’s environmental prerequisites and service status, required page fields, user account status, and permission ownership. If the external service is unavailable or rejects the request, retain organizational security requirements, record the visible error, and hand it to that service’s administrator.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

After the selected method is saved and enabled, users can authenticate through its entry. Whether accounts are created or synchronized in the product and which party controls permissions depends on the authentication type and permission configuration selected by the administrator.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the method cannot be selected, permission ownership is unclear, or test results conflict with account-lifecycle requirements, ask the product, system, and identity-service administrators to confirm the solution together. Share only the product version, selected method, test time, and redacted visible result.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.
