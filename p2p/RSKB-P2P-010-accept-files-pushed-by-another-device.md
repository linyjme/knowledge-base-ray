---
id: RSKB-P2P-010
title: Accept files pushed by another device
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
- How do I permit another device to push content to my computer?
- Why is an incoming P2P item rejected by the receiving client?
- Which receive permission is separate from browsing and fetching remote content?
keywords:
- incoming P2P reception
- pushed content
- receive permission
- remote device sender
- p2p
- Raysync
legacy_ids:
- FAQ-P2P-009
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-009 | How do I allow other devices to send files to me?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Accept files pushed by another device

## Short answer

In version 8.1.8.7 and later, enable P2P and turn on **Allow receive files from others** in P2P settings. This permission is on by default when P2P is enabled. Set a safe receive path and share your device ID only with the intended sender.

In versions before 8.1.8.6, open **Receive** and enable **Allow to receive files**, then copy the displayed device ID to the sender.

## Transfer-direction boundary

A pushed receive is initiated by the other device. It is separate from browsing the remote device and fetching selected content yourself.

## Version differences

The current permission label belongs to version 8.1.8.7 and later. Versions before 8.1.8.6 use **Allow to receive files** on the Receive page or client. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

## Important notes

Allowing incoming sends does not require you to expose a browsable file list. Store received files in a dedicated folder rather than a system or important-data directory.
