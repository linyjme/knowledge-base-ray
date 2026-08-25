---
id: RSKB-IAM-015
title: 'Identity administration: what to do when an external identity service is unavailable'
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
- How can users sign in when the LDAP service is down?
- What should I do during an OIDC identity-provider outage?
- How should users be notified of a third-party authentication outage?
keywords:
- identity service outage
- LDAP unavailable
- OIDC failure
- incident communication
- local administrator
- what to
- do when
- an external
legacy_ids:
- KB-USER-009
safety_tags:
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/user-integration/KB-USER-009-external-identity-service-unavailable.md
  section: What to do when an external identity service is unavailable?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identity administration: what to do when an external identity service is unavailable

## Short answer

During an external identity-service outage, new sign-ins that depend on that method usually fail or cannot complete. First confirm the impact scope, ask the identity-service administrator to restore service, and follow the organization’s existing local-administrator and incident procedures while retaining existing authentication controls and account-approval requirements.

## Scope and evidence

This applies when LDAP/AD, OpenID Connect, Email, System, or External HTTP Authentication has simultaneous failures, timeouts, or redirect problems for several users. For a single-user failure, troubleshoot the account first rather than declaring a service outage.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

1. Record the first discovery time, affected authentication method, number of affected users, customer-visible error, and last successful time.
2. Verify once with an organization-approved low-privilege test account, and check the identity service’s public status or contact its administrator to confirm an outage.
3. Check that time and network between the product and identity service are normal, but do not change security policies or trust settings as a temporary workaround.
4. Tell users which entry is affected, the current status, and the next update time to avoid repeated sign-ins that cause account lockouts or add incident load.
5. If the organization has a preconfigured authorized local administrator, that administrator can sign in to the admin console to review configuration and user impact. This does not automatically give regular integrated users another sign-in method.
6. After service recovery, first verify sign-in, sign-out, and permissions with the test account, then notify users and review failures from the incident period.

## Interpretation and recovery boundary

If the identity service reports normal status, recheck account mapping, redirect information, certificate validity, time, and network for the authentication method. All administrator access must continue using organization-approved independent accounts and existing permissions.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The incident is correctly classified and assigned to the appropriate identity-service administrator. After service and connectivity recover, users who depend on that method can authenticate again.

## Escalation

If several users continue to fail, service status cannot be confirmed, no existing local administrator is available, or some users still fail after recovery, escalate to the product administrator, identity-service administrator, and technical support. Provide only the version, time, impact scope, and redacted visible error.

