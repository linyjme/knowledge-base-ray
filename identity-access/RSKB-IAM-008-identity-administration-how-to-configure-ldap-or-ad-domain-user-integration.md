---
id: RSKB-IAM-008
title: 'Identity administration: how to configure LDAP or AD domain user integration'
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
- How do I configure LDAP user sign-in?
- How do I integrate an AD domain with the system?
- How should I enter the domain server address and base DN?
keywords:
- LDAP
- AD domain
- OpenLDAP
- base DN
- connection test
- configure LDAP
- or AD
- domain user
legacy_ids:
- KB-USER-002
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/user-integration/KB-USER-002-how-to-configure-ldap-ad.md
  section: How to configure LDAP or AD domain user integration?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identity administration: how to configure LDAP or AD domain user integration

## Short answer

Under “Sign-in Authentication” in “User Integration,” an administrator can enable LDAP/AD Domain and enter connection, directory-scope, and account information for the selected domain type. First use the page test to confirm a successful connection, then save and verify sign-in with a regular directory account.

## Prerequisites

This applies to version 8.1.8.7 environments with LDAP/AD Domain functionality. The operator needs product administrator permission and should obtain the exact domain server address, directory scope, bind account or domain administrator account, and required certificates from the directory administrator. Grant the account only the permissions required for directory queries.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **configure LDAP or AD domain user integration** in the intended deployment, edition, and component.

## Effect

Under “Sign-in Authentication” in “User Integration,” an administrator can enable LDAP/AD Domain and enter connection, directory-scope, and account information for the selected domain type. First use the page test to confirm a successful connection, then save and verify sign-in with a regular directory account.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Go to “User Integration > Sign-in Authentication,” enable “LDAP/AD Domain,” and open its settings.
2. Enter a name and domain server address, then select “AD Domain” or “OpenLDAP.”
3. For AD Domain, enter the base DN, administrator display name, and administrator password as shown. If the organization requires a secure connection, upload a valid domain server certificate through the interface.
4. For OpenLDAP, enter the bind user, bind password, and domain account path.
5. Use organization, user, and group filters to restrict the directory scope allowed for import and sign-in. Also confirm that the directory sign-in identifier matches the expected product account to avoid duplicate accounts caused by naming differences.
6. Click “LDAP Test.” After a successful test, save and configure authorization settings such as the default user role for this authentication method.
7. Verify sign-in and account mapping with a low-privilege test account before enabling automatic synchronization or bulk import.

## Recovery boundary

Check the domain type, server address, directory scope, account format, account status, password, and certificate validity period in order. Confirm normal network connectivity and time synchronization between the product server and directory service. If testing fails, record the error category shown on the page and do not repeatedly try a locked directory account.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

The page reports successful testing and saving. Accounts within the directory scope and filter conditions can authenticate through LDAP/AD Domain. Product permissions after import or first sign-in depend on administrator-configured roles and memberships.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the base DN, filters, certificate, or directory account permissions must be determined, or testing repeatedly fails, ask the product and directory administrators to work together. Provide the product version, selected domain type, test time, and redacted visible error. Do not provide passwords or private certificate content.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

