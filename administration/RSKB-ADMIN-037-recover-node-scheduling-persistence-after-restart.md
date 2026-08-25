---
id: RSKB-ADMIN-037
title: Recover node scheduling persistence after restart
product: raysync
components: [node-scheduler, client-manager]
domain: administration
access_level: internal
audience: [administrator, internal-engineer, support-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which persistence stage explains disappeared settings?
- Did restart recovery expose a failed reload?
- How is configuration that reverts compared with scheduler state?
- How do I compare saved settings to a failed reload?
- Which saved settings failed to reload?
- How are disappeared settings, saved state, failed reload, and recovery evidence separated?
- Across persistence recovery evidence and boundaries, how do scheduler configuration reverts distinguish state not written from state not loaded?
keywords: [settings disappeared saved reload, failed reload, scheduler configuration reverts, state written loaded, persistence recovery evidence]
legacy_ids: []
safety_tags: [authorization, sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-034, RSKB-TROUBLE-010]
source_refs:
- {file: source_file/persistence.md, section: What to do about node scheduling persistence issues, evidence_type: technical-boundary-document}
- {file: source_file/persistence-recovery.md, section: Task persistence and restart recovery, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Recover node scheduling persistence after restart

## Short answer

Compare the last confirmed write with the first confirmed load. A restored task record may return to waiting, remain final, or require a controlled retry; it does not promise unconditional byte-level resume.

## Terminology and boundaries

**Configuration** is intended durable state; **settings revert** describes an observed loss after **restart**. **Write**, **save**, and **persist** concern durable storage, whereas **load** and **reload** reconstruct runtime state. This vocabulary separates the two failure families without prescribing database-level intervention.

## Preconditions

An authorized operator must confirm the exact target scheduler environment, change time, expected saved state, available storage, affected task inventory, and approved restart window. Stop concurrent administration of the same settings.

## Recovery boundary

Preserve a protected backup through the approved product mechanism and retain redacted before-and-after inventories. Do not edit a database, remove records, or create overlapping retries while ownership and last state are uncertain.

## Controlled action

Confirm the exact target and effect. Correct only an evidenced permission, capacity, format, version, or load-order issue using the supported procedure, then perform one controlled restart and one minimum reversible state change.

## Verification

Verify that settings survive another controlled load, task records retain expected states, workers register, no duplicate task appears, and target files are independently checked. This recovery model is not a supported public contract and does not authorize raw storage edits.
