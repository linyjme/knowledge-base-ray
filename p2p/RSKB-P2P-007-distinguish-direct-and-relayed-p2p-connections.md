---
id: RSKB-P2P-007
title: Distinguish direct and relayed P2P connections
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
- Why does one peer transfer connect directly while another uses relay?
- What does the STUN service do during P2P network detection?
- How can UDP reachability affect hole punching between devices?
keywords:
- STUN
- UDP/3478
- network detection
- hole punching
- What does STUN do for P2P transfers?
- direct connection
- relay
- transfer log
legacy_ids:
- FAQ-P2P-015
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-016 | What does STUN do for P2P transfers?
  evidence_type: generated-faq
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-015 | How can I tell whether a P2P transfer is direct or relayed?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Distinguish direct and relayed P2P connections

## Short answer

Raysync performs network detection and attempts a direct client-to-client path. If the network cannot establish that path, the configured P2P infrastructure can forward traffic. In either case, the documentation says the file data is not uploaded to server disk.

Connection type became available in P2P transfer logs in 8.1.8.3. Ordinary users can see task progress and details in the client; access to server transfer logs may require an administrator.

## Version differences

P2P connection-type logging was added in 8.1.8.3. The 8.1.8.7 page redesign changes task presentation, not the underlying direct-path goal.

## Important notes

Do not infer “direct” merely from a successful task. Network topology and NAT can require relay. The source does not provide an end-user control that forces a direct path.

## Related documented boundaries

- **What does STUN do for P2P transfers?:** STUN is optional server-side configuration that detects the network between two devices and helps establish a direct connection. It improves the success rate of direct P2P connections. An administrator can configure a private STUN service or an open public one.
