---
id: RSKB-P2P-001
title: Prepare network and ports for peer-to-peer transfer
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
- Which TCP and UDP ports must the network team allow for P2P?
- Why does peer transfer fail when both clients are already online?
- What NAT and firewall preparation does an administrator need for P2P?
keywords:
- TCP 3443
- UDP 3478
- UDP 32003
- P2P firewall
- direct connection
- NAT mapping
legacy_ids:
- FAQ-P2P-001
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-003 | Which ports are required for peer-to-peer transfer?
  evidence_type: generated-faq
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-001 | What is peer-to-peer transfer used for?
  evidence_type: generated-faq
- file: raysync-user-faq/06-peer-to-peer-transfer.md
  section: FAQ-P2P-002 | What must be ready before I use peer-to-peer transfer?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Prepare network and ports for peer-to-peer transfer

## Short answer

Peer-to-peer transfer moves files between two running Raysync clients. The data is not uploaded to the Raysync server's disk. Raysync detects the network path and, when possible, transfers directly between the sender and receiver; server infrastructure can provide connection or traffic relay services when needed.

The current page also lets trusted devices browse permitted remote files, send local files, or fetch remote files. These actions depend on permissions set by the remote device.

## Network prerequisites

The documented core P2P ports are exactly:

- **TCP 3443** for the TCP forwarding server monitor used by peer-to-peer transfer.
- **UDP 3478** for the Raysync STUN service used for network detection and hole punching.
- **UDP 32003** for the peer-to-peer transfer service.

For an on-premises service behind NAT, the administrator or network team must provide the corresponding router mapping and host-firewall rules. For public-cloud deployment, they must also allow the ports in the applicable security group. These documented prerequisites do not incorporate optional multi-channel transfer port lists from other features, and they contain no deployment-specific addresses.

## Version differences

Version 8.1.8.7 introduced a redesigned P2P page with **My Computer**, **Remote Computer**, device connection, and a **Transfer Center**. Versions before 8.1.8.6 use the documented older Send/Receive workflow. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

## Important notes

P2P still requires the Raysync service, open ports, an online client, and administrator configuration. “Peer-to-peer” does not mean that every network will achieve a direct path.

## Related documented boundaries

- **Which ports are required for peer-to-peer transfer?:** The core P2P prerequisites are TCP 3443, UDP 3478, and UDP 32003. Opening or mapping them is an authorized administrator or network-team task.
- **What must be ready before I use peer-to-peer transfer?:** Both users must be logged in, both Raysync clients must be running, and both networks must be able to reach the configured service. The administrator must configure the P2P service address and required ports. For the workflow in version 8.1.8.7 and later, both devices enable P2P; the receiver shares a device ID and enables the permission needed for the intended action.
