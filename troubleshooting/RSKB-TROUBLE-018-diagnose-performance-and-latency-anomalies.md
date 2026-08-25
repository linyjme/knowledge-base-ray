---
id: RSKB-TROUBLE-018
title: Diagnose performance and latency anomalies
product: raysync
components:
- desktop-client
- client-manager
- file-service
domain: troubleshooting
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: null
  to: null
version_status: uncertain
status: active
question_variants:
- Why is throughput lower only for one target while comparable transfers remain normal?
- How can support separate a license-imposed cap from congestion, storage, or host
  resource limits?
- Which baseline proves whether proxy latency or the target service caused a slowdown?
- Why is throughput slow through the proxy but normal on the direct route?
- Does a flat transfer-rate ceiling indicate a license limit?
- Why is the same transfer slow through a proxy route?
- Does a steady speed ceiling come from a license limit rather than the network?
keywords:
- performance baseline
- latency jitter
- license throughput cap
- packet loss
- resource saturation
- target-specific slowdown
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
- license-control
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/performance-or-latency-abnormal.md
  section: What to do if performance or latency anomalies occur
  evidence_type: technical-boundary-document
- file: source_file/speed-anomaly.md
  section: What to do if the transmission speed is abnormal
  evidence_type: technical-boundary-document
- file: source_file/speed-anomaly(1).md
  section: Abnormal transmission speed
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose performance and latency anomalies

## Short answer

Build a comparable baseline before tuning. Keep ordinary slow transfer, a license throughput cap, and a port or connectivity failure separate; each has different evidence and corrective ownership.

## Symptoms

Throughput falls, latency increases or jitters, one target is slow, traffic is pinned to a fixed ceiling, or the transfer cannot establish data flow at all.

## Checks

Record version, edition and activation state, systems, roles, fixed sample, target, concurrency, success rate, first-byte time, total time, CPU, memory, storage, connection counts, packet loss, congestion, and security changes. Compare the same sample and window through the approved route and an organization-approved baseline. Repeat at least three times without mixing targets or concurrency.

## Interpretation

- **Direct and proxied paths are slow:** the target service owner coordinates the network owner comparing loss and latency with the storage owner checking endpoint throughput; change only the evidenced bottleneck and verify both paths against the same baseline.
- **Only the proxied path is slow, with client resource pressure:** the client owner reduces one supported client load variable or restores the previous route setting; verify client resources and proxy throughput with the same sample.
- **Server resource pressure is present:** the server owner corrects one evidenced CPU, memory, storage, or concurrency constraint within documented limits; verify the server counters and target checksum before accepting the change.
- **Counters remain stable while the application waits:** the application owner traces queue, task-state, and response timing without tuning the network; verify that the same request advances and reaches a terminal state.

Ordinary slow transfer can affect both direct and proxy paths and varies with source, destination, host, proxy, or network conditions. A license throughput cap stays near the documented ceiling and requires license-owner evidence, not network tuning. A port or connectivity failure prevents the data path rather than merely lowering throughput. These branches remain separate from scheduler non-dispatch and task-state problems.

## Backup or recovery boundary

Save the original supported settings and baseline as the recovery boundary. Do not bypass organizational networking, certificates, or security controls. Change one variable at a time and restore the previous value when improvement is not stable.

## Corrective action

An authorized operator must confirm the exact target workload, host roles, edition, policy, and setting. Confirm the expected effect, then adjust only one supported variable or route the license issue to the license owner; preserve the rollback value.

## Verification

Post-action verification repeats the same target sample and records success, throughput, latency, resource use, terminal state, failure set, and target checksum. Compare post-action results with the original baseline before accepting improvement.

## Evidence to collect

Collect masked version and edition, activation-status category, sample size, concurrency, timing series, resource summaries, packet-loss category, route category, and target checksum. Use `<host>`, `<path>`, and `<license-status>` placeholders.

## Escalation

Escalate when a stable cap contradicts documented licensing, when a single supported variable cannot isolate the anomaly, or when integrity or production availability is affected.
