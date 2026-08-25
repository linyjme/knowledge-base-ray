---
id: RSKB-P2P-004
title: Browse and fetch files from a remote device
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
- How can I browse files shared by a remote P2P device?
- Where do I choose the local destination for a fetched remote file?
- Why is remote browsing unavailable even though device connection works?
keywords:
- P2P browsing
- remote file list
- fetch permission
- local destination
- remote computer
legacy_ids:
- FAQ-P2P-008
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-008 | How do I fetch files from a remote device?
  evidence_type: generated-faq
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-010 | How do I allow another device to browse and fetch my files?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Browse and fetch files from a remote device

## Short answer

Select permitted remote content and choose the local destination before creating the fetch task.

## Transfer-direction boundary

Browsing and fetching means the local user selects content exposed by the remote device. It is separate from accepting files pushed by another device.

## Prerequisites

- Connect successfully to the remote device.
- The remote device has enabled **Allow others to fetch files**.
- Your local destination has enough storage space.

## Steps

1. In **Remote Computer**, select the files or folders to fetch.
2. In **My Computer**, navigate to the local destination.
3. Select **Receive** to create the fetch task, or drag the remote items into the local area.
4. Monitor the task in **Transfer Center**.

This is a pull operation: the remote device must enable **Allow others to fetch files**. It is different from passively accepting files that another device sends to you.

## Version differences

Remote browsing and explicit fetching are documented for version 8.1.8.7 and later. Versions before 8.1.8.6 use a Receive page that prepares the device to accept sender-created tasks. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

## Important notes

Choose a local destination with sufficient space. Access to view a remote file list does not by itself grant permission to fetch those files.

## Related documented boundaries

- **How do I allow another device to browse and fetch my files?:** Enable **Allow others to view file list** so connected devices can browse files under your configured open path. Then enable **Allow others to fetch files** if they should be able to download those files. Viewing and fetching are separate permissions: browsing alone does not authorize download.
