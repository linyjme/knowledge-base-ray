---
id: RSKB-TROUBLE-005
title: Troubleshoot P2P relay connection and reception
product: raysync
components:
- user-portal
- desktop-client
domain: troubleshooting
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
- Why does my P2P task use relay instead of a direct connection?
- What should I check when another device cannot receive pushed files?
- How can STUN or network restrictions affect peer connectivity?
keywords:
- P2P relay
- direct connection
- transit traffic
- STUN
- Why does a peer-to-peer transfer show a relay connection instead of direct?
- P2P failed
- device ID
- offline
legacy_ids:
- FAQ-TROUBLE-010
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-010 | Why does a peer-to-peer transfer show a relay connection instead of direct?
  evidence_type: generated-faq
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-011 | Why does my peer-to-peer transfer fail to connect or complete?
  evidence_type: generated-faq
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-012 | Why can’t another device send files to my computer?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Troubleshoot P2P relay connection and reception

## Short answer

Raysync supports direct and relay connection types in P2P transfer logs. Based on the P2P and firewall documentation, a relay result means the direct path was not used and server forwarding/transit was involved. Raysync states that P2P data is not uploaded to server disk; the server carries transit traffic.

## Likely cause

The two devices could not establish the preferred direct connection under their current networks. STUN is optional but is documented as improving the success rate of direct connections; P2P also depends on its configured service and ports.

## What the user can check

Confirm both clients are online, P2P is enabled, and normal network connectivity exists. Reconnect the device. Do not change STUN or firewall settings yourself.

## When to contact an administrator

Contact the administrator if relay is unexpected or materially affects performance. Provide the task and connection type so they can check P2P, STUN, and forwarding configuration.

## Version differences

Version 8.1.8.3 added P2P connection type to transfer logs.

## Important notes

The explanation of relay as server transit is an inference from the documented direct/relay log types, P2P transit statement, and forwarding port.

## Related documented boundaries

- **Why does my peer-to-peer transfer fail to connect or complete?:** P2P requires both sender and receiver to be logged in, running the client, online, and enabled for P2P. The receiver must allow incoming files, and the sender needs the current device ID or email.
- **Why can’t another device send files to my computer?:** Your client must be online with P2P enabled and **Allow receive files from others** turned on. The receiving computer also needs sufficient storage and a valid receive save path.
