---
id: RSKB-P2P-002
title: Enable P2P and manage the local device ID
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
- Where can I find the device ID for my local P2P client?
- Can I refresh or copy the identifier shown for my computer?
- Why must P2P be enabled before another device can connect?
keywords:
- Support point-to-point transmission on PC
- device ID
- copy ID
- update ID
- Where do I find my P2P device ID, and can I change it?
- Enable P2P
- user portal
- desktop client
legacy_ids:
- FAQ-P2P-004
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-078 | Support point-to-point transmission on PC
  evidence_type: feature-matrix
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-005 | Where do I find my P2P device ID, and can I change it?
  evidence_type: generated-faq
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-004 | How do I enable peer-to-peer transfer on my device?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-079 | Support update device ID
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Enable P2P and manage the local device ID

## Short answer

Start and log in to the Raysync client, open **Peer to Peer** from the left menu, and turn on **Enable P2P** in the upper-right corner. The page then displays your device ID and local file list and allows connections to remote devices.

## Version differences

This toggle and page layout apply to the redesigned interface in version 8.1.8.7 and later. In versions before 8.1.8.6, use the documented **Send** or **Receive** page; the receiver turns on **Allow to receive files** instead of using the redesigned page-level toggle. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

## Important notes

The administrator must already have configured the P2P service, and your account must be allowed to use it. Do not turn off P2P during a transfer because the connection may be interrupted.

## Related documented boundaries

- **Support point-to-point transmission on PC:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Where do I find my P2P device ID, and can I change it?:** In version 8.1.8.7 and later, enable P2P and locate **My Device ID** at the top of the P2P page. Select **Copy** to copy it for a trusted partner. Select **Update** to generate a new device ID.
- **Support update device ID:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
