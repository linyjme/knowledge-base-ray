---
id: RSKB-P2P-003
title: Connect a remote device and send P2P files
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
- How do I connect to a remote device and push files to it?
- What device ID should the sender enter for a P2P connection?
- Why can I connect to a computer but still be unable to send a file?
keywords:
- P2P device connection
- device ID
- remote computer
- send task
- recipient email
legacy_ids:
- FAQ-P2P-006
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-006 | How do I add and connect to a remote device?
  evidence_type: generated-faq
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-007 | How do I send files to another device in 8.1.8.7 or later?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-083 | Supports moving from source path to target path
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Connect a remote device and send P2P files

## Short answer

Connect from the **Remote Computer** area by using the other device's ID or email.

## Prerequisites

- Both devices are online with P2P enabled.
- You have the remote device ID or email.
- The remote device has enabled the permission required for the intended transfer.

## Steps

1. In **Remote Computer**, select **Connect Device**.
2. Enter the remote device ID or email and, optionally, a device name.
3. Select **Connect**.
4. After connection, select the device from the device list and confirm that the remote area shows only the content its permissions allow.

## Version differences

This persistent remote-device workflow belongs to the redesigned page in version 8.1.8.7 and later. Versions before 8.1.8.6 ask for the receiver's ID or email directly while creating a send task. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

## Important notes

Receiving files and browsing/fetching files are different permissions. A device can accept pushed files without exposing a browsable file list. If a known device is offline, wait until it is online before connecting.

## Related documented boundaries

- **How do I send files to another device in 8.1.8.7 or later?:** Select local content, choose the permitted remote destination, and create the send task.
- **Supports moving from source path to target path:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
