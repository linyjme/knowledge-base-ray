---
id: RSKB-STORAGE-002
title: Understand group speed limits and storage quotas
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
- Why is my upload blocked after a personal or group quota is reached?
- How do group speed limits differ from storage capacity limits?
- Who can increase the quota assigned to my account or group?
keywords:
- quota
- maximum storage capacity
- storage full
- upload blocked
- What happens when I reach my personal or group storage quota?
- speed limit
- bandwidth
- group folder
legacy_ids:
- FAQ-STORAGE-006
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-007 | What happens when I reach my personal or group storage quota?
  evidence_type: generated-faq
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-006 | Why is my upload or download speed limited in a group folder?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand group speed limits and storage quotas

## Short answer

Raysync lets administrators limit upload and download speed for a space member or group file library. The documented default is unlimited, but a configured limit can make group-folder transfers slower than transfers in another area or for another user.

## Capacity boundary

A personal quota belongs to one user, while a group quota belongs to the shared group folder. Backend storage exhaustion is a separate capacity condition; raising a user or group quota cannot create space in an exhausted storage backend.

## Version differences

The release list records group file-library speed limits in version 6.7.8.3. Legacy space management describes upload and download limits, while the 8.1.8.0 and later group-management guide states that group libraries can control transfer speed.

## Important notes

A configured limit is not necessarily a network fault. Upload and download limits are documented as separate values. Compare only transfers made under the same account, group, and policy. If the observed rate appears inconsistent with the assigned limit, give the administrator the group-library name and task details.

## Related documented boundaries

- **What happens when I reach my personal or group storage quota?:** Personal and group quotas apply to different owners. A personal quota is assigned to a user in the current space; in 8.1.8.0 and later, the current user-role guide calls this **Maximum storage**. A group quota belongs to the shared group file library rather than to one member. The release history states that users and group file libraries support maximum storage capacity. When a configured limit is exceeded, new files are no longer stored; existing files are not described as being automatically removed merely because the quota is exceeded.
