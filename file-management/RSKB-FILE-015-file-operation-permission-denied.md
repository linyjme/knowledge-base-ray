---
id: RSKB-FILE-015
title: Why do I not have permission for a file operation?
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
  - Why is a file action missing or denied in Raysync?
  - Why can another user upload or delete here but I cannot?
  - How do group membership permissions affect file operations?
keywords: [permission denied, file permission, group permission, missing action, access control]
legacy_ids: [FAQ-FILE-015]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-008, RSKB-FILE-009, RSKB-FILE-014]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-015 | Why does Raysync say I do not have permission for a file operation?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Why do I not have permission for a file operation?

## Short answer

Raysync limits file operations through account permissions and, in a group file library, the permissions attached to group membership. Upload, download, folder, sync, share, and delete actions can therefore differ between users and locations.

A missing or denied action means the applicable permission set does not include that operation. The evidence does not document an end-user override. Record the affected library or path and the denied operation, then ask the administrator or authorized group owner to review your access instead of attempting to bypass it.
