---
id: RSKB-FILE-010
title: Why can I not see hidden files in the file list?
product: raysync
components: [user-portal]
domain: file-management
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Why are dotfiles missing from Raysync?
  - Can I display files whose names begin with a dot?
  - Why can a hidden file not be transferred?
keywords: [hidden files, dotfiles, file visibility, file list, transfer restriction]
legacy_ids: [FAQ-FILE-010]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-015]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-010 | Why can I not see hidden files in the file list?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Why can I not see hidden files in the file list?

## Short answer

An administrator can enable **Do not show hidden files** for your account or role. When it is enabled, Raysync does not display files whose names start with `.`. The current user-role documentation also says files covered by this setting cannot be transferred.

This restriction has no documented end-user override. Ask the administrator to confirm whether it applies to your account or role. A hidden file is not deleted, recycled, isolated, or overwritten; it is excluded from the file list and, under the documented current setting, from transfer.
