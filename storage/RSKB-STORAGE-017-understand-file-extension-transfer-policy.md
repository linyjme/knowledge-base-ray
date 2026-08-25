---
id: RSKB-STORAGE-017
title: Understand file-extension transfer policy
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
- Why is a file extension rejected before transfer begins?
- How do whitelist and blacklist rules affect uploads?
- Who can change the allowed file-format policy for my account?
keywords:
- file format
- whitelist
- blacklist
- extension
- upload filter
- Why is Raysync blocking files with a particular extension?
- storage
- Raysync
legacy_ids:
- FAQ-STORAGE-005
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-005 | Why is Raysync blocking files with a particular extension?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand file-extension transfer policy

## Short answer

Your personal or group policy may use a transfer file-format allowlist or blocklist. An allowlist permits only configured extensions; a blocklist rejects configured extensions. The legacy guide shows multiple formats separated with semicolons, such as `txt;iso;mp4`.

## Version differences

The release list introduces group file-library upload format blacklists and whitelists in version 6.8.8.2. For legacy versions from 6.8.8.2 through before 8.1.8.0, the space/member guide documents the allowlist and blocklist behavior. For 8.1.8.0 and later, the user-role guide documents the same model for personal policies, while the current group-management guide confirms filtering for group libraries.

## Important notes

Changing an extension does not change file content and should not be used to evade policy. Ask the administrator whether the file type is allowed and what approved format or workflow should be used.
