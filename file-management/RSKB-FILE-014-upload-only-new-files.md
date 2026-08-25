---
id: RSKB-FILE-014
title: Why can I upload only new files?
product: raysync
components: [user-portal, desktop-client]
domain: file-management
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Why is an upload rejected when the filename already exists?
  - What does Only upload new files mean?
  - Will a rejected same-name upload overwrite the target?
keywords: [only upload new files, same filename, rejected upload, existing target, upload restriction]
legacy_ids: [FAQ-FILE-014]
safety_tags: []
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-001, RSKB-FILE-015]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-014 | Why can I upload only new files?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Why can I upload only new files?

## Short answer

The **Only upload new files** restriction allows an upload only when the destination does not already contain a file with that name. A same-name upload is rejected rather than replacing the existing file.

The target remains unchanged after that rejection. This behavior is different from an overwrite policy. If the setting prevents a required upload, ask the administrator or authorized file owner to review the destination and applicable upload policy; the evidence provides no end-user override.
