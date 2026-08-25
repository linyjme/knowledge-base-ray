---
id: RSKB-P2P-006
title: Create offline and scheduled P2P send tasks
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
- Can I queue a P2P send while the receiving device is offline?
- How do I schedule a peer transfer for a later time?
- Why is an offline send task waiting instead of transferring immediately?
keywords:
- Supports sending offline tasks
- Support scheduled sending
- receiver offline
- ready for transfer
- queued task
- Can I create a P2P send task while the receiver is offline?
- scheduled sending
- once
legacy_ids:
- FAQ-P2P-013
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-082 | Supports sending offline tasks
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-084 | Support scheduled sending
  evidence_type: feature-matrix
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-013 | Can I create a P2P send task while the receiver is offline?
  evidence_type: generated-faq
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-014 | Can I schedule a P2P send task?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Create offline and scheduled P2P send tasks

## Short answer

In the documented pre-8.1.8.6 legacy workflow, yes. The sender can create a task while the receiver is offline. Its status is **Receiver offline, ready for transfer**, and the receiver automatically receives the file after coming online.

## Version differences

Offline P2P tasks were added in version 6.8.8.1 and are explicitly described in the guide for versions before 8.1.8.6. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support. The workflow in version 8.1.8.7 and later requires both devices to be online before connecting and does not document creating an offline task.

## Important notes

An offline-ready task still depends on the receiver later starting the client and allowing reception. The cited sources do not provide extra recovery steps for an offline task that never starts.

## Related documented boundaries

- **Supports sending offline tasks:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported The source records 6.8.8.1 as an appearance or change milestone, not as proof of the onset of support.
- **Support scheduled sending:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Can I schedule a P2P send task?:** Configure a send task to run once or on a repeating schedule from the current P2P task settings.
