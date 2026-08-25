---
id: RSKB-INTEGRATION-002
title: SDK CLI and manager responsibility boundaries
product: raysync
components: [sdk, cli, client-manager, file-service]
domain: integrations-api
access_level: internal
audience: [developer, internal-engineer, support-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which caller boundary transfers a recurring operation?
- Does the scheduled synchronization job remain under control-plane ownership?
- What exists once the shell has returned to a schedule?
- How is terminal lifetime related to recurring work?
- Why can scheduled synchronization, command closure, manager ownership, and job persistence diverge?
- How do shell return, schedule existence, and synchronization lifetime relate?
keywords: [scheduled synchronization command manager job, shell returned schedule exists, synchronization lifetime, invocation boundary, recurring ownership]
legacy_ids: []
safety_tags: [sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-INTEGRATION-001, RSKB-ADMIN-031]
source_refs:
- {file: source_file/sdk-cli-capability-boundary.md, section: Differences in capabilities between SDK and synchronization command line, evidence_type: technical-boundary-document}
- {file: source_file/sdk-cli-roles.md, section: 'Roles of SDK, synchronization command line and manager', evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# SDK CLI and manager responsibility boundaries

## Short answer

The SDK and synchronization CLI both use the local manager control chain, but they are not capability mirrors. The SDK exposes integration and callback surfaces; the CLI emphasizes scriptable persistent synchronization; the manager owns task lifecycle; and the transfer client moves files.

## Terminology and boundaries

The **shell** owns an invocation session, and **CLI exits** describes that caller ending. **Scheduled synchronization persists** when durable work remains with the manager; **manager lifetime** is therefore separate from caller lifetime. This internal distinction does not promise persistence for every command or mode.

## Entry distinctions

An SDK one-time transfer is not the same intent as a CLI synchronization task configured to run once. Remote directory operations in the SDK do not imply an identically named CLI command. A CLI process exiting does not delete or stop a manager-owned persistent task.

When diagnosing an integration, identify the actual entrance before interpreting its result: parameter parsing, SDK connection, manager acceptance, remote login, worker execution, terminal state, and target verification are separate stages. A standalone direct file client is a different execution surface from the manager persistence chain.

## Publication boundary

This role model is not a supported public contract. It does not authorize task deletion, process control, callback-memory assumptions, or undocumented equivalence between SDK, CLI, manager, and direct-file-client operations.
