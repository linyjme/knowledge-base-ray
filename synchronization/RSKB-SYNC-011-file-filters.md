---
id: RSKB-SYNC-011
title: How do sync file filters work?
product: raysync
components: [user-portal, desktop-client]
domain: synchronization
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - How can I include or exclude matching files from synchronization?
  - Can a wildcard blacklist skip names with a common prefix?
  - Why are the synchronization filter controls locked?
keywords: [sync filter, whitelist, blacklist, wildcard, size filter]
legacy_ids: [FAQ-SYNC-011]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-007, RSKB-SYNC-012]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-011 | How do sync file filters work?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-069 | Filtering of specified files
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do sync file filters work?

## Short answer

Sync filters allow or exclude files and folders that match configured conditions. Wildcards are supported; for example, a blacklist entry of `test*` filters names beginning with `test`. A separate size filter can skip files above the configured size.

Confirm whether each rule is a whitelist or blacklist, because reversing it changes which content transfers. If controls are missing or locked, an administrator may have prohibited user-defined filters or assigned fixed rules through the user's role.

## Availability

Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB.
