---
id: RSKB-START-008
title: Understand P2P and transfer-control release boundaries
product: raysync
components:
- user-portal
domain: getting-started
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
- Which release records the transfer-list filter I need?
- Why is the exact 8.1.8.6 transfer workflow not assigned by the guides?
- When were Linux, multi-channel transfer, and client link tasks recorded?
keywords:
- web tasks
- client tasks
- filtering
- multi-channel
- sync
- Which Raysync 8.1.8.x release supports the transfer control I need?
- P2P
- 8.1.8.6
legacy_ids:
- FAQ-VERSION-007
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-011 | Which Raysync 8.1.8.x release supports the transfer control I need?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-007 | Where is the peer-to-peer transfer workflow boundary around versions 8.1.8.6 and 8.1.8.7?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-027 | Support file transfer with http web (support drag file and pause, cancel a task)
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand P2P and transfer-control release boundaries

## Short answer

The clear release boundary is version 8.1.8.7. The release list, dated 2026-07-07, records a redesigned peer-to-peer transfer page, and the current workflow guide requires a client at version 8.1.8.7 or later. The quick-start source separately labels an earlier workflow for versions before 8.1.8.6.

Exactly version 8.1.8.6 is not assigned to either workflow by those labels. The evidence therefore supports three statements only: before 8.1.8.6 uses the documented earlier flow; 8.1.8.7 and later uses the redesigned flow; and exactly 8.1.8.6 is a documentation gap.

## Version differences

The quick-start sources label their flows "Version 8187+" and "Version Before 8186." Because neither source assigns exactly 8.1.8.6, do not classify it as legacy or redesigned solely from a neighboring release.

## Important notes

If support for exactly version 8.1.8.6 is required, report the full client and server versions and ask the administrator or Raysync support which workflow that deployed build uses. This FAQ intentionally states only the release boundary and does not reproduce interface instructions.

## Related documented boundaries

- **Which release records each transfer-control change?:** The release history associates client-free web-task pause or cancel controls with 8.1.8.1, the Linux desktop client with 8.1.8.2, real-time sync updates with 8.1.8.3, link upload or download in the desktop client with 8.1.8.4, and multi-channel transfer, task sorting, and creation-time filtering with 8.1.8.6. It associates task-name and task-status filtering and a desktop-client sync improvement with 8.1.8.7. These are documented release milestones, not universal minimum-support guarantees. For client-free web pause or cancel, the feature matrix instead records 6.3.8.0; that history is unresolved, so no introduction version is selected.
