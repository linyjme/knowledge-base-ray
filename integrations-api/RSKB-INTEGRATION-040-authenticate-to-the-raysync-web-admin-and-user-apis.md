---
id: RSKB-INTEGRATION-040
title: Authenticate to the Raysync Web Admin and User APIs
product: raysync
components:
- admin-portal
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
- How do I encode a password for the Web Admin or User API?
- Where do I put the JWT after a successful portal login?
- What happens if I change hashid_salt in config.ini?
keywords:
- Hashids
- hashid_salt
- Authorization
- Bearer
- JWT
- refresh_token
- config.ini
legacy_ids: []
safety_tags:
- credentials
- authorization
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-041
- RSKB-INTEGRATION-042
- RSKB-INTEGRATION-043
- RSKB-INTEGRATION-044
- RSKB-INTEGRATION-045
- RSKB-INTEGRATION-046
- RSKB-INTEGRATION-047
- RSKB-INTEGRATION-048
- RSKB-INTEGRATION-049
- RSKB-INTEGRATION-050
- RSKB-IAM-011
source_refs:
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: API interface authentication mode description
  evidence_type: api-reference
- file: API/8187/Raysync Web User API Documentation v8.1.8.7.md
  section: API interface authentication mode description
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Authenticate to the Raysync Web Admin and User APIs

## Short answer

Encode the password with Hashids (string to bytes, bytes to hex, then Hashids), call the login path, then send `Authorization: Bearer <token>` on later requests. The Web Admin and Web User API documents in this repository still label themselves v8.1.8.4 inside the 8.1.8.7 folder.

## Password encoding

The portal APIs authenticate every request. Login bodies send a Hashids ciphertext, not the raw password.

1. Convert the password string to bytes.
2. Convert those bytes to hexadecimal.
3. Encode the hex string with Hashids.

Salt comes from `config.ini` field `hashid_salt` (example format `hashid_salt = eRuYuw`). Default Hashids length is **64** characters.

**Note:** Modifying `hashid_salt` affects normal background login. To log in to the background normally after a change, delete the `hashid_salt` configuration.

Do not copy sample salts, encoded passwords, or JWT strings from examples into tickets. Use `<password>`, `<hashid_salt>`, and `<token>`.

## Using the token

After login succeeds, the response includes `token` and `refresh_token`. Subsequent calls use:

```text
Authorization: Bearer <token>
```

Admin login is `POST /api/users/admin/login`. User login is `POST /api/user/login`. Admin token renewal is `PUT /api/users/admin/auth`. User token renewal is `PUT /api/user/auth` with `Authorization: Bearer <refresh_token>`.

The User API documents the new `token` as valid for 1 hour and `refresh_token` as valid for 7 days.

## Admin login extras

Admin login fields: `account` (necessary), `password` (Hashids ciphertext, necessary), `isAuth` (optional boolean). `isAuth` is disabled by default; when enabled, the `hashid_salt` value from `config.ini` is used.

A successful admin login returns `token`, `refresh_token`, `userId`, lockout fields, and version fields. Web portal success uses HTTP JSON `code` **200**, which is not the Client API `code` **0**.

## Related documented boundaries

- **Admin license and services:** `RSKB-INTEGRATION-041`
- **User login, refresh, and logout:** `RSKB-INTEGRATION-049`
