---
id: RSKB-TROUBLE-011
title: Resolve a node identifier conflict
product: raysync
components:
- node-scheduler
- typhoonv6
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
- Why do two scheduler entries appear to share one node identity while names alternate?
- What evidence identifies the legitimate host before duplicate registration is removed?
- How can support recover when jobs appear to reach the wrong execution node?
keywords:
- node identity conflict
- identity digest
- duplicate registration
- host ownership
- wrong execution node
- snapshot clone
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/identity-conflict.md
  section: What to do if node identifier conflicts?
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Resolve a node identifier conflict

## Short answer

Prove ownership before changing identity state. Compare identity digest, last connection time, host ownership, and installation source; a matching display name alone is not a conflict.

## Symptoms

The scheduler shows multiple entries for one unique identity, names alternate, or a task appears on the wrong execution node. Pause new identity-dependent work and preserve both entries and their timeline.

## Checks

Compare the redacted identity digest, connection times, host ownership, package origin, snapshot or image history, and registration history. Determine whether an environment was copied, a snapshot restored, identity material reused, or a duplicate registration created.

## Interpretation

One identity tied to different verified hosts is a conflict. Two similar display names with distinct identity digests are not. Unclear ownership means neither entry is safe to delete or regenerate.

## Backup or recovery boundary

Back up the identity summaries, registration records, and task attribution. This is the recovery boundary: confirm the exact target and preserve the legitimate identity before removing a duplicate or regenerating the erroneous copy.

## Corrective action

Only an authorized node administrator may act. Confirm the exact target duplicate, correct node, host ownership, effect on assigned tasks, and recovery copy. After explicit confirmation, suspend the uncertain object and remove only the proven duplicate registration or regenerate only the erroneous copy.

## Verification

Post-action verification requires the scheduler target list to contain only expected identities, the correct node to remain stable, two consecutive snapshots to agree, and one controlled task to produce verifiable target evidence on the intended host.

## Evidence to collect

Collect redacted identity digests, host-role labels, connection times, installation source, snapshot history, affected task IDs as placeholders, and before-and-after registration counts. Never share raw identity material.

## Escalation

Escalate without deletion when ownership cannot be proven, assigned work cannot be recovered, or the conflict returns after a controlled cleanup.
