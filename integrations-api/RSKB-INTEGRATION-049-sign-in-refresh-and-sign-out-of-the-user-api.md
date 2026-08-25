---
id: RSKB-INTEGRATION-049
title: Sign in refresh and sign out of the User API
product: raysync
components:
- user-portal
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
- How does a user portal integration log in through POST /api/user/login?
- How long are User API token and refresh_token valid?
- Which authWay values can I send on user login?
keywords:
- /api/user/login
- /api/user/auth
- /api/user/logout
- authWay
- refresh_token
- emailCode
legacy_ids: []
safety_tags:
- credentials
- authorization
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-040
- RSKB-INTEGRATION-050
- RSKB-START-002
- RSKB-IAM-007
source_refs:
- file: API/8187/Raysync Web User API Documentation v8.1.8.7.md
  section: User
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Sign in refresh and sign out of the User API

## Short answer

`POST /api/user/login` with a Hashids password. Optional `authWay` selects the identity source. Use `PUT /api/user/auth` with the refresh token to obtain a new access token. `POST /api/user/logout` ends the session. Documented access-token lifetime is 1 hour; refresh-token lifetime is 7 days.

## Paths

| Method | Path | Purpose |
| --- | --- | --- |
| POST | `/api/user/login` | User login |
| PUT | `/api/user/auth` | Renew token (`Authorization: Bearer <refresh_token>`) |
| POST | `/api/user/logout` | User logout |

Login necessary fields: `account`, Hashids `password`. Optional: `emailCode`, `authWay`.

Documented `authWay` values: 1 local user, 2 LDAP user, 4 email user, 8 system user, 64 OIDC user, 128 HTTP user, 256 OAuth user.

A successful login `data` object includes `token`, `refresh_token`, `userId`, `accountType`, lockout fields, and version fields. `accountType` values documented on the success payload include 1 administrator, 2 general user, 3 sharing account, 4 LDAP/AD, 5 email, 6 Linux system, 7 enterprise WeChat, 8 OIDC, 9 external HTTP.

A documented login failure example uses `code` 1005 and `value` `Password invalid`, with `loginFailTimes` incremented.

## Confirmation

After login, call an authorized User API route such as share-link list with `Authorization: Bearer <token>`. After refresh, discard the previous access token. After logout, the previous token should no longer authorize requests; if a call still succeeds, treat that as unspecified and stop using the old token.

Encode passwords as in `RSKB-INTEGRATION-040`. Never log JWT strings.
