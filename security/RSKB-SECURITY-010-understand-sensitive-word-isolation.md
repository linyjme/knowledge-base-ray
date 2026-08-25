---
id: RSKB-SECURITY-010
title: Understand sensitive-word isolation
product: raysync
components:
- user-portal
- file-service
domain: security
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
- Why was a file isolated after its name matched a sensitive term?
- Can sensitive-word detection inspect text-file content during transfer?
- Who can review the configured term that triggered isolation?
keywords:
- Support sensitive word detection
- sensitive words
- file name
- text file
- isolation
- transfer
- Why was my file isolated for a sensitive-word match?
- security
legacy_ids:
- FAQ-SECURITY-014
safety_tags:
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-121 | Support sensitive word detection
  evidence_type: feature-matrix
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-014 | Why was my file isolated for a sensitive-word match?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand sensitive-word isolation

## Short answer

Raysync can inspect a file name and the content of a text file during transfer. If either contains a configured sensitive word, the system automatically places the file in the isolation area. The matching terms are configured by an administrator.

## Version differences

The release list records sensitive-word detection in version 6.5.8.0. Both the legacy and 8.1.8.0 and later guides describe the same user-visible result: a configured match in a file name or text-file content sends the file to isolation.

## Important notes

Do not evade the policy by renaming, encoding, or resubmitting the file. A match may concern the name or text content, so a filename-only review is insufficient. Provide the file name, transfer time, and displayed isolation information to the administrator for an authorized review.

Administrators can configure multiple sensitive terms, so the policy is not limited to a single documented example.

## Related documented boundaries

- **Support sensitive word detection:** SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
