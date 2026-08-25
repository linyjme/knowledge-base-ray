---
id: RSKB-IAM-016
title: 'Identity administration: what is the difference between local and integrated users'
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
- What is the difference between a local account and an LDAP account?
- Who manages an integrated user’s password?
- Is the product account automatically locked or deleted when the source system disables it?
keywords:
- local user
- integrated user
- password ownership
- account lifecycle
- deactivation and permission revocation
- what is
- the difference
- between local
legacy_ids:
- KB-USER-010
safety_tags:
- authorization
- destructive-operation
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/user-integration/KB-USER-010-local-and-integrated-users.md
  section: What is the difference between local and integrated users?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identity administration: what is the difference between local and integrated users

## Short answer

Local users are created and maintained in the product by a product administrator. Integrated users come from a directory or external identity service and can form customer-visible accounts through import, synchronization, or first sign-in. Successful authentication does not grant authorization automatically. If Sign-in Authentication uses product-controlled permissions, check account status, roles, and spaces in the product. If External HTTP or another method uses external-service-controlled permissions, the external service returns and manages authorization. Disabling a source account does not mean every product account is automatically locked or deleted. For immediate revocation, perform the applicable deactivation and permission removal at both the source and product according to account type.

## Prerequisites

This applies to administrators planning account creation, offboarding, password support, and permission audits. Whether an integration method creates a user in the account list, supports synchronization, and which party controls permissions varies. First review the current selection on the Sign-in Authentication page.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Effect

Source-side deactivation blocks the corresponding external authentication according to that identity system. Product-side deactivation and removal of roles or space permissions separately revoke product access; neither step automatically deletes the other account or its stored content.

## Confirmation

Confirm the exact person and both account identifiers, authentication method, authorization owner, existing product roles and spaces, required retention, and immediate revocation scope before changing either system.

## Procedure

1. Identify the account source: a product administrator creates a local user; LDAP/AD, OIDC, Email, System, or external authentication identifies an integrated user.
2. Confirm credential ownership: local user passwords follow product security policy; integrated-user credentials are normally managed by the corresponding directory or identity service, depending on the method.
3. Confirm the creation method: directory users can be imported or synchronized in bulk; some external methods form account information on first sign-in, while others do not create users in the account list.
4. Confirm authorization ownership: for product-controlled permissions, check product account status, user roles, group relationships, and space memberships. For external-service-controlled permissions, investigate authorization returned and managed by the external service. In neither case does successful authentication imply automatic authorization.
5. For a synchronized directory account, after source-side deactivation check product account status according to the configured synchronization policy and actual synchronization result. Source deactivation alone does not mean the product account is immediately locked or deleted.
6. For a product account formed on first sign-in, source-side deactivation affects subsequent external authentication but does not uniformly delete the product account. Administrators must still review and revoke unneeded status, roles, and space permissions in the product.
7. For a mode that does not create a local account and uses external-service-controlled permissions, block authentication or revoke authorization at the external service and confirm on Sign-in Authentication that this mode is actually selected.
8. For immediate revocation, perform the applicable account deactivation or authorization revocation at the source and the applicable deactivation and permission revocation for any existing product account. Verify both results and record the changes.

## Recovery boundary

If account source or authorization ownership is unclear, first check the user type under Account Information and the permission-control selection on Sign-in Authentication, then ask the identity administrator. If the source account is disabled but the product account remains, check synchronization results, product status, and permissions separately instead of recreating or deleting an account with the same name.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

Administrators can assign authentication, synchronization, deactivation, and permission revocation to the correct owner according to account creation and authorization ownership. Actual source and product states are both verified, and users retain only the access required for their work.

## Escalation

If an offboarded account can still sign in, status differs after synchronization, one person has multiple accounts, or revocation ownership is unclear, ask the product and identity administrators to review it together. Provide a redacted account identifier, authentication method, permission-control selection, last synchronization time, and currently visible source and product status.
