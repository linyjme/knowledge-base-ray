---
id: RSKB-IAM-014
title: 'Identity administration: why an integrated user has no space or permission after successful sign-in'
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
- What should I do if an LDAP user cannot see a file space after signing in?
- Why does a synchronized user have no upload or download permission?
- Why are features unavailable after a third-party user authenticates?
keywords:
- authentication and authorization
- space member
- user role
- account status
- permission assignment
- why an
- integrated user
- has no
legacy_ids:
- KB-USER-008
safety_tags:
- authorization
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/user-integration/KB-USER-008-synced-user-has-no-space-or-permission.md
  section: Why an integrated user has no space or permission after successful sign-in?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identity administration: why an integrated user has no space or permission after successful sign-in

## Short answer

Successful authentication proves only that the user’s identity is valid; it does not grant product-resource permissions automatically. An integrated user must also have an active account, belong to the appropriate space or membership scope, and receive a user or group role appropriate for the work.

## Prerequisites

This applies when a user can enter the product after directory import, automatic synchronization, or first external sign-in but cannot see spaces, file libraries, or action buttons. Authorized administrators should assign roles and spaces according to least privilege.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Effect

Changing an existing user's role, group membership, space membership, or account-level permission changes that user's product authorization. Changing a default role affects later account creation but does not automatically rewrite every existing user.

## Confirmation

Confirm the exact user, account source, target space, current and intended role or permission, whether the change is individual or default, and a least-privileged test before saving.

## Procedure

1. Under “Account Information,” confirm that the user was created or synchronized, has a normal account status, and is not locked.
2. Confirm that the user belongs to the expected space and has a valid space membership. If no usable storage is configured for the space, the space administrator must configure it first.
3. Check that the user role includes the required features. If access comes through a group, also check group membership and group role.
4. For an integrated user automatically created on first sign-in, check that the default user role for that authentication method is correct.
5. For an existing user, adjust permissions individually on the account or space-members page. Changing a default role normally does not rewrite all existing users automatically.
6. Ask the user to sign out and sign in again, then verify the target space and permitted operations.

## Recovery boundary

Compare the account status, membership, user role, and group role of the affected user with a working user in the same space. Do not grant high privileges just to test; add only business-required permissions and record the change.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

When authentication succeeds and the account, space membership, and role are valid, the user can see authorized spaces and features. Unauthorized resources remain hidden or unavailable.

## Escalation

If the user is absent from the account list, the space has no usable storage, a role lacks required permission, or the current administrator cannot adjust membership, contact the product or space administrator. Provide a redacted user identifier, space name, expected operation, current role, and visible message.
