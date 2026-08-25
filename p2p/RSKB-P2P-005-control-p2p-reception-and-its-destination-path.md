---
id: RSKB-P2P-005
title: Control P2P reception and its destination path
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
- Where are files received from another P2P device saved?
- How do I change the local destination for incoming peer transfers?
- Can I stop other devices from pushing files to this client?
keywords:
- receive path
- save path
- local destination
- Where are received P2P files saved?
- Support for closing peer-to-peer file reception
- Support for setting the path for receiving files
- stop receiving
- disable P2P
legacy_ids:
- FAQ-P2P-011
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-012 | Where are received P2P files saved?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-081 | Support for closing peer-to-peer file reception
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-080 | Support for setting the path for receiving files
  evidence_type: feature-matrix
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-011 | How do I stop receiving P2P files?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Control P2P reception and its destination path

## Short answer

In version 8.1.8.7 and later, turn off **Allow receive files from others** when you no longer want pushed files. You can also turn off **Enable P2P** to close P2P on the device entirely. In versions before 8.1.8.6, clear **Allow to receive files** on the user portal's **Receive** page or turn off receiving in the Raysync client.

## Version differences

The redesigned permission names apply to version 8.1.8.7 and later. Versions before 8.1.8.6 use the documented older receive control. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

## Important notes

Do not disable P2P while an active transfer is running because it may interrupt the connection. Disabling incoming sends does not automatically disable remote browsing or fetching; turn off those permissions separately if they were enabled.

## Related documented boundaries

- **Where are received P2P files saved?:** In version 8.1.8.7 and later, use **Save path when receiving files** in P2P settings to choose the default destination for pushed files. For files you fetch yourself, navigate to the desired directory in **My Computer** before selecting **Receive** or dragging the remote items there. Versions before 8.1.8.6 document preparing the Receive page but do not specify a user-selectable save path.
- **Support for closing peer-to-peer file reception:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Support for setting the path for receiving files:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
