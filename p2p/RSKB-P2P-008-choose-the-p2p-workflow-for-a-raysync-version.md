---
id: RSKB-P2P-008
title: Choose the P2P workflow for a Raysync version
product: raysync
components:
- desktop-client
domain: p2p
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
- Which P2P screen should I use for my installed Raysync version?
- Why is there no documented workflow for exactly version 8.1.8.6?
- How does the redesigned Raysync 8.1.8.7 device page differ from older Send and Receive pages?
keywords:
- 8.1.8.7
- 8.1.8.6
- legacy P2P
- workflow
- Which P2P workflow should I use for my Raysync version?
- p2p
- Raysync
legacy_ids:
- FAQ-P2P-017
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-017 | Which P2P workflow should I use for my Raysync version?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Choose the P2P workflow for a Raysync version

## Short answer

Check your deployed Raysync version, then choose the matching workflow:

1. For **version 8.1.8.7 and later**, open **Peer to Peer**, enable P2P, connect the remote device by ID or email, and send or fetch files between **My Computer** and **Remote Computer**. Monitor the result in **Transfer Center** and the client task list.
2. For **exact version 8.1.8.6**, match the controls visible in your deployed interface, or contact your administrator or Raysync support. The supplied sources do not unambiguously specify an operational workflow for this exact version.
3. For **versions before 8.1.8.6**, use the documented legacy **Send** and **Receive** pages. Some older documentation also refers to a transfer ID and key.

## Exact-version gap

Exactly version 8.1.8.6 is a documentation gap. The approved evidence assigns versions before 8.1.8.6 to the earlier flow and 8.1.8.7 or later to the redesigned flow. No behavior from either adjacent range should be assumed for exactly 8.1.8.6.

## Version differences

The release list explicitly dates the page redesign to 8.1.8.7 and P2P system notifications to 8.1.8.6.

## Important notes

The quick-start heading says “Before 8186,” while the page redesign begins at 8187, leaving 8.1.8.6 without an explicit workflow in the supplied documentation. No behavior from either adjacent range should be assumed for that exact version.
