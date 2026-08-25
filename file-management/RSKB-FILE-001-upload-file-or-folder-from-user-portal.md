---
id: RSKB-FILE-001
title: How do I upload a file or folder from the user portal?
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
  - How can I upload through the Raysync web portal?
  - Where do I choose a file or folder for browser upload?
  - How do I start a web upload without the client?
keywords: [web upload, upload file, upload folder, user portal, transfer progress]
legacy_ids: [FAQ-FILE-001]
safety_tags: [authorization, destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-002, RSKB-FILE-006, RSKB-FILE-014]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-001 | How do I upload a file or folder from the user portal?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do I upload a file or folder from the user portal?

## Short answer

Open the destination in **My Files** or an accessible **Group File Folder** library. Select **Upload file with web** for a file or **Upload folder with web** for a folder, choose the local content, and monitor progress in the web transfer list at the bottom-right of the page.

## Authorization and preconditions

Use an account with upload permission for the selected **My Files** or **Group File Folder** directory. Confirm that the local source is readable and that the destination's same-name policy is understood. Web folder upload does not create an empty source folder.

## Exact target and effect

Identify the exact destination directory and the exact local file or folder before opening the web-upload control. The intended effect is one upload into that directory. If the destination policy overwrites a same-name file, its prior content is replaced; a reject policy leaves it unchanged.

## Confirmation

Before starting, confirm the displayed destination, selected local object, expected target name, and conflict policy. Do not broaden the selection after that review.

## Recovery boundary

Keep the local source until target verification is complete. Before an allowed overwrite, preserve the existing target through the organization's approved backup or recovery policy; the supplied portal evidence does not define recovery for overwritten content.

## Post-action verification

Monitor the web transfer list to a final result, then verify the expected object in the exact destination. Check its name, size, and business readability; for a folder, confirm the expected non-empty hierarchy.

## Before you start

You need upload permission for the destination. Web folder upload does not upload an empty folder.

## Steps

1. Open the destination directory in the user portal.
2. Select **Upload file with web** or **Upload folder with web**.
3. Choose the local file or folder.
4. Monitor the upload in the web transfer list.

## Important limitation

If the destination policy overwrites a same-name file, the upload can replace that file's content. A policy can instead reject a same-name upload. Confirm the destination, name, and applicable conflict policy before starting.
