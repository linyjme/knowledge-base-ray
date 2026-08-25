---
id: RSKB-INTEGRATION-050
title: Create list and cancel share links over the User API
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
- How do I create a share-download or invite-upload link with the User API?
- What does shareUrlType 0 versus 1 mean?
- How does a user cancel a share link through PATCH /api/share/link/cancel?
keywords:
- /api/share/link/create
- /api/share/link/list
- /api/share/link/cancel
- shareUrlType
- shareFiles
- allowDelete
legacy_ids: []
safety_tags:
- credentials
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-049
- RSKB-INTEGRATION-047
- RSKB-SHARE-001
- RSKB-SHARE-002
- RSKB-SHARE-007
source_refs:
- file: API/8187/Raysync Web User API Documentation v8.1.8.7.md
  section: Share link
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Create list and cancel share links over the User API

## Short answer

Create a link with `POST /api/share/link/create`, list with `GET /api/share/link/list`, and cancel with `PATCH /api/share/link/cancel`. `shareUrlType` **0** is upload (invite-upload); **1** is download (share-download). Do not mix those features. The User API documents cancel, not delete.

## Paths

| Method | Path | Purpose |
| --- | --- | --- |
| POST | `/api/share/link/create` | Create share link under user space |
| GET | `/api/share/link/list` | Get user share link |
| PATCH | `/api/share/link/cancel` | Cancel external link (`shareUrlList`) |

All require `Authorization: Bearer <token>` from user login.

## Create fields

Necessary fields documented on create include `shareFiles`, `needPassword`, `shareUrlPasswd`, `shareEmail`, `shareUrlType`, `shareAllowDownload`, `shareServerPath`, `shareEmailContent`, `shareExpireTime`, `accountType`, `shareBaseUrl`, `notifyEmail`, `shareSrcType`, `account`, and `emailLanguage` (0 Chinese, 1 English).

`shareSrcType`: 0 file, 1 directory, 2 multiple files. `shareAllowDownload`: 0 not allowed, 1 allowed. `accountType` for specified authentication: 2 local, 4 AD/OpenLDAP, 5 email, 7 enterprise WeChat, 8 OIDC, 9 external HTTP.

Optional fields include `inviteMemberType` (0 owner, 1 designated internal members), `userList`, `fileAlias`, `deptList`, `allowDelete` (invite-upload deletion; 0 disallowed, 1 allowed), `downloadLimit` (0 unlimited, or 1–99999), `emailSendTime`, `emailSendSwitch`, `sharePrivateEmail`, and `externalEmail`.

Do not log `shareUrlPasswd`, recipient emails, or full share URLs.

## Cancel versus admin delete

User cancel sends `shareUrlList` of link URLs. The User API does not document a delete route. Administrator delete is `DELETE /api/share/link/delete` in `RSKB-INTEGRATION-047`.
