---
id: RSKB-STORAGE-015
title: Understand group-member file permissions
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
- Which file actions can a group member perform in a shared folder?
- Why can I download a group file but not rename or delete it?
- Who controls upload and management permissions for group members?
keywords:
- group permissions
- upload
- download
- delete
- rename
- member
- Why can another group member perform a file action that I cannot?
- storage
legacy_ids:
- FAQ-STORAGE-003
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-003 | Why can another group member perform a file action that I cannot?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand group-member file permissions

## Short answer

Raysync supports different file-operation permissions for members of the same group file library. Administrators can control operations such as listing personal files, downloading, deleting, renaming, creating folders, uploading, creating sync tasks, moving, copying, creating an invite-upload link, and creating a share-download link.

## Version differences

Legacy space management documents configuration per group member. In the 8.1.8.0 and later navigation, administrators can create **Group permission** definitions and assign them to group file libraries. The visible user outcome is the same: an unavailable button or denied operation may reflect your assigned permission.

## Important notes

Do not use another member’s account to work around a restriction. If your role requires the action, give the group administrator the group-library name and the exact missing or denied operation.
