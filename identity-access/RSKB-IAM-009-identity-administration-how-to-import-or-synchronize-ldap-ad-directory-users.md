---
id: RSKB-IAM-009
title: 'Identity administration: how to import or synchronize LDAP/AD directory users'
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
- How do I import LDAP users in bulk?
- Can AD domain accounts be synchronized automatically?
- Should I import users only or organizations and groups too?
keywords:
- directory user
- bulk import
- automatic synchronization
- organization and group
- duplicate account
- import or
- synchronize LDAP/AD
- directory users
legacy_ids:
- KB-USER-003
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/user-integration/KB-USER-003-how-to-sync-or-import-directory-users.md
  section: How to import or synchronize LDAP/AD directory users?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identity administration: how to import or synchronize LDAP/AD directory users

## Short answer

After the LDAP/AD connection is tested and saved, an administrator can bulk-import directory accounts under “Account Information.” AD Domain can also configure automatic account synchronization in Sign-in Authentication settings. You can import users only or import users, organizations, and groups together.

## Prerequisites

This applies to version 8.1.8.7 environments where LDAP/AD Domain is enabled and successfully tested. Before a bulk operation, confirm directory scope, filters, user-count limits, default user roles, and group roles. Verify the result with a small test set first.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **import or synchronize LDAP/AD directory users** in the intended deployment, edition, and component.

## Effect

After the LDAP/AD connection is tested and saved, an administrator can bulk-import directory accounts under “Account Information.” AD Domain can also configure automatic account synchronization in Sign-in Authentication settings. You can import users only or import users, organizations, and groups together.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Complete the LDAP/AD Domain connection and directory-scope configuration and confirm a successful test.
2. For manual import, go to “Account Information” and select the LDAP import function.
3. Select “Import Users Only” or “Import Users, Organizations, and Groups.” The latter replaces the existing top-level organization and creates the corresponding domain organization name. It also creates group file-library names in the default space for imported groups and associates group users with those file libraries. Before proceeding, confirm the impact on the existing organization plan, default space, and related users.
4. For periodic synchronization, enable “Automatic Account Synchronization” in LDAP/AD Domain settings, select the frequency, and choose users only or users, organizations, and groups.
5. After execution, check the account list, organization/group membership, account status, default roles, and available spaces.
6. Directory accounts from the same source are matched by account. Subsequent imports or synchronization retain one account and update synchronizable information. If an account or email conflicts with another existing account, use the actual page failure to identify the existing account and its source, resolve the conflict, and then import again instead of repeating the operation.

## Recovery boundary

Confirm that LDAP/AD testing still succeeds, check whether filters exclude the target account, and verify the user-count limit. For missing or abnormal accounts, compare their account, email, directory status, and existing account list before repeating a broad import.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

The page reports a successful import, and users within the scope and filters appear in the account list. When organizations and groups are imported, the previous top-level organization is replaced, and the corresponding group file-library names and user associations in the default space are visible in the customer interface. Subsequent synchronization runs at the saved frequency and scope.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the import changes the existing organization structure, account or email conflicts occur, the user limit is exceeded, or synchronization differs from the directory, pause the bulk operation and contact the product and directory administrators. Provide the import time, selected import method, affected count, and redacted visible failure information.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

