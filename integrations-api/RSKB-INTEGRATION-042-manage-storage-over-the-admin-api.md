---
id: RSKB-INTEGRATION-042
title: Manage storage over the Admin API
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
- How do I create local or object storage with the Web Admin API?
- Which OssType values does POST /api/storage/create accept?
- How do I list or delete storage through the Admin API?
keywords:
- /api/storage/create
- /api/storage/list
- /api/storage/delete
- OssType
- AccessKeySecret
legacy_ids: []
safety_tags:
- credentials
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-040
- RSKB-STORAGE-012
- RSKB-STORAGE-013
- RSKB-STORAGE-014
source_refs:
- file: API/8187/Raysync Web admin API Documentation v8.1.8.7.md
  section: StorageResource
  evidence_type: api-reference
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-18'
  verified_by: documentation-review
---

# Manage storage over the Admin API

## Short answer

Create storage with `POST /api/storage/create`, list with `GET /api/storage/list`, and delete with `DELETE /api/storage/delete`. `OssType` selects the backend. Hashids-encrypt `AccessKeySecret`. Never log real access keys.

## Paths

| Method | Path | Purpose |
| --- | --- | --- |
| POST | `/api/storage/create` | Create storage |
| GET | `/api/storage/list` | List all storage |
| DELETE | `/api/storage/delete` | Delete storage |

All three require an administrator Bearer token.

## Create fields

Necessary: `OssType`, `storageName`. Documented `OssType` values:

- 0 local storage
- 1 Alibaba Cloud OSS
- 2 Amazon S3
- 3 other S3 storage
- 5 Azure Blob
- 7 Google Cloud Storage

The documentation does not define `OssType` 4 or 6.

Local storage uses `OssHome` and optional cleanup fields (`cleanSwitch`, `cToFolder`, `cProperty`, `cTimeDelta`, `cFileType`, `cDelete`, `cReserveAfterCleanTime`). Cloud storage uses `Endpoint`, `AccessKeyId`, Hashids `AccessKeySecret`, `BucketName`, optional `Region`, `OssBuff`, and `UseVirtualAddressing` (0 or 1).

`cReserveAfterCleanTime` range is 0–9999 days; 0 means permanent retention. `cFileType` 1 (transfer temporary files) is allowed only when `cProperty` is 0.

## Confirmation and recovery

List storage after create and confirm the new `storageName` and type. Before delete, confirm the storage is not still assigned to users. Deleting storage is destructive; this API document does not describe recovering deleted storage objects.
