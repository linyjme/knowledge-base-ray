---
id: RSKB-FILE-013
title: Why is my uploaded file shown in the Isolation Zone?
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
  - Why is my upload missing from its destination folder?
  - Was my uploaded file quarantined by Raysync?
  - How can I handle a file moved to the isolation zone?
keywords: [Isolation Zone, missing upload, quarantined file, antivirus detection, sensitive words]
legacy_ids: [FAQ-FILE-013]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-011, RSKB-FILE-015]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-013 | Why is my uploaded file missing from its user portal folder and shown in the isolation zone?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Why is my uploaded file shown in the Isolation Zone?

## Short answer

When Raysync isolates an upload, it moves the file out of its intended user-portal folder and into the Isolation Zone. That is why it is absent from the original destination.

The isolation view can show the file name, isolation time, and detected virus type where applicable. Isolation is not normal deletion, recycle-bin retention, overwrite, or permanent removal.

The supplied evidence does not document an end-user release or restore action. Ask the administrator to review the isolated item; do not repeatedly upload the same file as a workaround.
