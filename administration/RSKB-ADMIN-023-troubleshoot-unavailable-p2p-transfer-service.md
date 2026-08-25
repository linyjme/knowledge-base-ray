---
id: RSKB-ADMIN-023
title: 'Administrator guide: how to troubleshoot an unavailable peer-to-peer transfer service'
product: raysync
components:
- admin-portal
domain: administration
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- What should I do if the peer-to-peer service is not running?
- Why is the P2P feature shown as unavailable?
- What should I check when a peer-to-peer task cannot connect directly?
keywords:
- peer-to-peer transfer service
- P2P unavailable
- Enterprise Edition
- service address
- STUN
- troubleshoot an
- unavailable peer-to-peer
- transfer service
legacy_ids:
- KB-SERVICE-006
safety_tags:
- authorization
- destructive-operation
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/service-configuration/KB-SERVICE-006-p2p-service-unavailable.md
  section: How to troubleshoot an unavailable peer-to-peer transfer service?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to troubleshoot an unavailable peer-to-peer transfer service

## Short answer

Peer-to-peer configuration in version 8.1.8.7 is limited by edition and requires a reachable server IP address and a port from 1025 through 65535. A domain name is not currently supported for this address. Peer-to-peer tasks may be unavailable when the service is not running, the network is unreachable, the configuration has not taken effect, or the current edition does not support it.

## Prerequisites

This applies when "Peer-to-Peer Transfer Service" shows "Not Running" in the admin console, peer-to-peer settings are locked, or a peer-to-peer task reports a service error, offline device, or connection failure. Peer-to-peer settings are available in Enterprise Edition.



## Effect

Saving a peer-to-peer server IP or port changes how devices reach the service. Restarting Peer-to-Peer Transfer Service temporarily interrupts peer connectivity while the saved configuration takes effect; it does not bypass edition or License restrictions.

## Confirmation

Confirm the exact service, approved reachable IP address, port from 1025 through 65535, optional trusted STUN endpoint, network exposure, active-task impact, and maintenance window before saving or restarting.

## Procedure

1. Confirm that the current edition and License support peer-to-peer functionality. Do not bypass edition or authorization conditions when settings are locked.
2. Ask an administrator to open "Peer-to-Peer Transfer Service" under "System Configuration" and verify the required server IP and port. The port must be from 1025 through 65535. For public use, enter an administrator-approved, externally reachable public server IP. Domain names are not currently supported.
3. If a STUN service is configured, confirm that its address and port come from a trusted source and are reachable. STUN assists network discovery and does not replace the peer-to-peer service itself.
4. Confirm that both devices' networks permit the required peer-to-peer communication and that the configured port does not conflict and is opened only to the minimum necessary scope.
5. After saving, restart Peer-to-Peer Transfer Service through the admin console as prompted, then return to the home page and confirm that the status is "Running Normally."
6. Reconnect the devices and create a small test task. Observe whether a direct connection or another product-supported connection method is established.

## Recovery boundary

Record service status, whether settings are locked, visible device status, connection type, and error time separately. An offline device, stopped service, and inability to establish a direct connection are different symptoms; do not determine the cause from only one.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

When edition conditions are met, the address and port are valid, the network is reachable, and the service restart succeeds, peer-to-peer status is "Running Normally," and devices can reconnect and start tasks.

## Escalation

If the edition does not support the feature, contact an administrator to evaluate upgrading to a supported edition. The administrator handles the address, port, network policy, and restart. Escalate to technical support if several devices still fail despite correct configuration.
