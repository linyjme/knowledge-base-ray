---
id: RSKB-STORAGE-001
title: Understand the purpose of a group folder
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
- What is a group folder used for in Raysync?
- How does a shared file library help team collaboration?
- Why are files in a group directory visible to multiple members?
keywords:
- group folder
- group file library
- collaboration
- shared directory
- What is a Raysync group folder used for?
- storage
- Raysync
legacy_ids:
- FAQ-STORAGE-002
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-002 | What is a Raysync group folder used for?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand the purpose of a group folder

## Short answer

A group folder is shared storage for multi-user collaborative file management. It provides one group file library in which authorized members work with the same shared content. The library can use an independent storage location rather than a member’s personal home directory. It can also be configured with a main directory or virtual directory and with storage-related transfer characteristics such as speed limits and file filtering.

Because it is shared storage, the group library remains a group resource when one member signs out or changes personal files. It is suitable for project, team, or exchange content that must be available to multiple members without placing it in one person’s private directory.

## Version differences

Legacy documentation calls the resource a group folder and explicitly describes independent storage for each group folder. The 8.1.8.0 and later guide calls it a group file library and continues to describe a shared file directory with configurable main and virtual directories. The storage purpose remains the same across the terminology change.

## Important notes

Choose a group library for genuinely shared content, not merely as extra personal capacity. Its storage, retention, filtering, or speed characteristics can differ from personal storage. Ask the group administrator which library owns the content before cleanup or migration; this FAQ does not enumerate member operations or portal workflow.
