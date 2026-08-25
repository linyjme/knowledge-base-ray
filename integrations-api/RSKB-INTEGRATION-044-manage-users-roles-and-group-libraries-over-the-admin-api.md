---
id: RSKB-INTEGRATION-044
title: Manage users roles and group libraries over the Admin API
product: raysync
components:
- admin-portal
- http-api
domain: integrations-api
access_level: support
audience:
- developer
- support-engineer
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- How do I create a user with the Web Admin API?
- Which Admin API path locks or copies a user?
- How do I list roles and group file libraries?
keywords:
- /api/users/create
- /api/users/lock
- /api/users/copy
- /api/permission/role/list
- /api/user/group/list
- roleId
- storageId
legacy_ids: []
safety_tags:
- credentials
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-040
- RSKB-IAM-018
- RSKB-IAM-024
source_refs:
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: UserResource
  evidence_type: api-reference
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: PermissionRoleResource
  evidence_type: api-reference
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: UserGroupResource
  evidence_type: api-reference
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: PermissionGroupResource
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Manage users roles and group libraries over the Admin API

## Short answer

Create users with `POST /api/users/create` using a Hashids password, `email`, `roleId`, and `storageId`. List, update, lock, copy, and delete through the `/api/users/*` paths. Role and group-library lists are separate GET routes. Deleting or locking a user is an authorized administrator action.

## User paths

| Method | Path | Purpose |
| --- | --- | --- |
| POST | `/api/users/create` | Create user |
| PUT | `/api/users/update` | Update user |
| GET | `/api/users/list` | Get all user information |
| GET | `/api/users/:user_id` | Get user information |
| DELETE | `/api/users/delete` | Delete user |
| PATCH | `/api/users/lock` | Lock user |
| POST | `/api/users/copy` | Copy user |

Necessary create fields: `account`, Hashids `password`, `email`, `roleId`, `storageId`. Optional fields include `home`, virtual directories (`vfs.alias`, `vfs.storageId`, `vfs.path`), first-login password reset (`needUpdatePwd`), email notification split (`emailNotificationType` 0 together / 1 separate), and `loginLinkType` (0 web and desktop, 1 website, 2 desktop client).

Do not record real passwords, emails, or home paths.

## Role and group lists

| Method | Path | Purpose |
| --- | --- | --- |
| GET | `/api/permission/role/list` | User role list |
| GET | `/api/user/group/list` | Group file library list |
| GET | `/api/permission/group/list` | Group file library permission list |

Use these list endpoints to obtain `roleId` and group identifiers before create or update. Do not invent role IDs.

## Confirmation

After create, `GET /api/users/:user_id` or `GET /api/users/list`. After lock, confirm the account can no longer sign in through the documented login path rather than assuming a side effect this API page does not state.
