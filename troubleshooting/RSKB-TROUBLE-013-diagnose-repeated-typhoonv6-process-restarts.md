---
id: RSKB-TROUBLE-013
title: Diagnose repeated TyphoonV6 process restarts
product: raysync
components:
- typhoonv6
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
- Why can a TyphoonV6 role look present while its worker exits and is relaunched repeatedly?
- Which evidence distinguishes an approved controlled restart from a continuous crash
  cycle?
- What host and package checks should precede recovery of a repeatedly exiting process?
- Can a service look healthy while its underlying process keeps restarting?
- Why does the transfer worker process restart every few seconds?
keywords:
- TyphoonV6 restart loop
- worker continuous exit
- controlled restart
- duplicate instance
- host resource pressure
- package integrity
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/process-restarts.md
  section: What to do if the TyphoonV6 process restarts repeatedly
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose repeated TyphoonV6 process restarts

## Short answer

A startup wrapper can hide repeated worker exits. Preserve the scene, distinguish a controlled restart from continuous exits, and correct host, account, package, or duplicate-instance causes before restarting one role.

## Symptoms

The role always appears present but start and exit times repeat, traffic stops, or connections return only briefly. The pattern may occur while idle or only after a connection.

## Checks

Record role, package, every start and exit time, exit category, connection and traffic state. Preserve redacted operating-system events, product logs, crash material, and state. Check duplicate instances, memory, writable storage, process limits, running-account permission, security interception, release-family match, and delivery-package integrity.

## Interpretation

An approved one-time lifecycle event is a controlled restart. Repeated exits in a short window are a crash cycle even if a wrapper relaunches the process. Idle exits favor host, account, or package causes; exits after connection favor version or peer-side correlation.

## Backup or recovery boundary

Retain the last failure scene, crash evidence, and known package and configuration snapshot as the recovery boundary. Do not delete logs or dumps, remove state, or let an automatic restart loop overwrite evidence. If the same failure repeats, an authorized service operator may pause automatic restart after confirming the exact role, affected process family, and evidence-preservation effect. Record the approved policy and its prior value before pausing. Automatic restart remains paused until an authorized corrective change is complete and recovery evidence supports restoration. Stop only a proven duplicate instance through the documented service control.

## Corrective action

An authorized service operator must confirm the exact target role, process family, package, running account, and expected effect. Apply one authorized corrective change to an evidenced external cause, then start the single role in documented order and suspend business traffic during observation. Complete a stable observation and one minimum request against the same role. If the same failure has not recurred, the authorized operator may restore automatic restart under the approved policy; this is the only re-enable path. If the same exit or reason recurs, keep automatic restart paused, preserve the new crash evidence, and escalate instead of restoring the policy.

## Verification

Post-action verification has two branches. **Recovered branch:** the same target process remains present through the stable observation, no new exit event occurs, the minimum request reaches terminal state, target evidence agrees, and the approved policy is restored and verified. **Recurrence branch:** if the same exit, reason, or continuous exits return, automatic restart remains paused; preserve crash evidence, record the repeated timeline, and escalate without returning business traffic.

## Evidence to collect

Collect masked version, platform, role, package source, start-exit timeline, exit categories, resource events, and before-and-after connection counts. Use `<host>`, `<role>`, and `<path>` placeholders and never send unredacted or unsanitized dumps.

## Escalation

Escalate when the same exit recurs after a clean documented start, the worker exits without external pressure, or package integrity cannot be established.
