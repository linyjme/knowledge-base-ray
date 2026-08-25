---
id: RSKB-FILE-016
title: Which file operations work without a running client?
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
  - What can I do in Raysync using only the browser?
  - Can I upload, download, or rename without the client?
  - Which file actions still require the desktop client?
keywords: [browser only, no client, web operations, web transfer, file management]
legacy_ids: [FAQ-FILE-016]
safety_tags: [authorization, destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-001, RSKB-FILE-003, RSKB-FILE-004, RSKB-FILE-007]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-016 | Which file operations work without a running client?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Which file operations work without a running client?

## Short answer

Using only the browser, the user portal supports creating a folder, invite upload, normal upload, normal download, share download, copy, move, delete, folder properties, and rename.

You can also pause or cancel web transfer tasks without a running client in the current version covered here.

Creating a sync-task directory and some video preview operations require a client. Web folder upload cannot upload an empty folder. Browser-only operations still require the corresponding permission, and destructive actions such as delete still follow the server's deletion policy.

A share-download link delivers content for download; an invite-upload link receives uploaded content. They are not interchangeable.
