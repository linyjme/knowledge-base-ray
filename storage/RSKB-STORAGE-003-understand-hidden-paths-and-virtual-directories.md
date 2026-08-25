---
id: RSKB-STORAGE-003
title: Understand hidden paths and virtual directories
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
- Why is a folder hidden or forbidden in my Raysync file view?
- How does an allowed path differ from a virtual directory?
- Who can expose a server path that my account cannot access?
keywords:
- forbidden path
- allowed path
- hidden folder
- access denied
- Why is a path hidden or unavailable in my Raysync files?
- virtual directory
- alias
- mapped path
legacy_ids:
- FAQ-STORAGE-008
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-008 | Why is a path hidden or unavailable in my Raysync files?
  evidence_type: generated-faq
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-009 | What is a virtual directory in Raysync?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand hidden paths and virtual directories

## Short answer

The administrator may have configured a forbidden access path or an allowed access path. A forbidden path is hidden and cannot be created in, deleted, renamed, copied, moved, uploaded to, or downloaded from. With allowed paths, only the configured files or folders are visible, and operations outside them are unavailable.

## Version differences

Allowed access paths are listed in the version 6.7.8.0 release. For legacy versions from 6.7.8.0 through before 8.1.8.0, the space/member guide describes both forbidden and allowed path controls. For 8.1.8.0 and later, the user-role guide documents the same controls for personal roles. Group-library path policy remains separately assignable.

## Important notes

The absence of a path can be intentional security policy, not data loss. Do not try alternate clients or path spellings to bypass it. Ask the administrator to confirm your authorized path scope.

## Related documented boundaries

- **What is a virtual directory in Raysync?:** A virtual directory is an administrator-added directory that appears in your file area under an alias and maps to a valid path in configured storage. A user can view, transfer, and operate files in it subject to permissions. Multiple virtual directories are supported.
