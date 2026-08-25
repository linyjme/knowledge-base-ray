---
id: RSKB-STORAGE-004
title: Identify storage exhaustion and available storage types
product: raysync
components:
- user-portal
- file-service
domain: storage
access_level: public
audience:
- end-user
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Why do uploads fail when the backend storage is exhausted?
- Which storage backends can a Raysync deployment use?
- How is server storage exhaustion different from my personal quota?
keywords:
- local storage
- OSS
- S3
- Azure Blob
- Google Cloud Storage
- Which storage types can be visible through Raysync?
- storage exhausted
- backend storage
legacy_ids:
- FAQ-STORAGE-010
safety_tags:
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-011 | Which storage types can be visible through Raysync?
  evidence_type: generated-faq
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-010 | What happens when the storage behind Raysync is exhausted?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identify storage exhaustion and available storage types

## Short answer

The supplied sources do not specify what an end user sees when the physical or object storage behind Raysync is exhausted. They document supported storage types, storage configuration, and statistics, but they do not define a reliable error message, automatic fallback, retry behavior, or recovery procedure for backend-capacity exhaustion. Therefore, an upload or file-operation error must not be labeled as underlying storage exhaustion from these sources alone.

## Capacity boundary

Backend storage exhaustion is separate from a personal quota or group quota. A quota can block one owner even when the backend has capacity, while an exhausted backend can block writes even when a quota remains.

## Version differences

Legacy documentation describes storage within spaces; the 8.1.8.0 and later guide documents local and several object-storage types in the later storage guide family. Neither guide family supplies a version boundary or end-user behavior for exhaustion of the underlying storage.

## Important notes

Preserve the exact error, target space/library and path, task time, file size, and whether other operations still work. Contact the administrator to check backend capacity and storage health. Do not repeatedly retry a large upload or delete shared data to “make room” without authorization; the sources do not establish that either action is the correct recovery.

## Related documented boundaries

- **Which storage types can be visible through Raysync?:** Depending on administrator configuration, files exposed through a personal or group directory can use local storage, Alibaba Cloud OSS, Amazon S3, S3-compatible storage, Azure Blob, or Google Cloud Storage. Raysync can configure multiple storages for the home and virtual directories of users and group file libraries.
