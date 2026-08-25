---
id: RSKB-TROUBLE-021
title: Explain a skipped or renamed transfer file
product: raysync
components:
- user-portal
- desktop-client
domain: troubleshooting
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
- Why was a transferred file skipped instead of overwritten?
- How does the same-name policy cause a received file to be renamed?
- Which filter can exclude a file from a transfer task?
keywords:
- skipped file
- renamed file
- filter
- same name
- overwrite
- Why was a file skipped or renamed unexpectedly during transfer?
- troubleshooting
- Raysync
legacy_ids:
- FAQ-TROUBLE-016
safety_tags:
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-016 | Why was a file skipped or renamed unexpectedly during transfer?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Explain a skipped or renamed transfer file

## Short answer

Raysync can skip files because of name/size filters, format allowlists or blocklists, "only download new files," or the pre-transfer unchanged-file check. It can rename a source or target when a same-name file already exists, depending on task or client settings.

## Likely cause

A configured regular-expression/size filter matched the file, the file extension is disallowed, the file kept changing during the 3–30-second pre-transfer check, or a same-name conflict selected **Rename file** instead of overwrite.

## What the user can check

Open the task’s file details and error reason. Review the task’s filter, file-processing, and same-name settings without changing them mid-diagnosis. Confirm whether the destination already contained that name.

## When to contact an administrator

Contact the administrator if the client forbids filter changes or a server/group policy controls formats. Provide the original name, resulting name, and task settings.

## Version differences

Legacy and current user guides document these behaviors; navigation and available policy ownership can differ after 8.1.8.0.

## Important notes

Do not delete either copy until content and timestamps are verified.
