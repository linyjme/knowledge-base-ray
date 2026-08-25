---
id: RSKB-CLIENT-009
title: Which editions provide bulk client task controls?
product: raysync
components:
- desktop-client
- client-manager
domain: client
access_level: public
audience:
- administrator
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Can an SMB client start, suspend, or delete every task in one operation?
- Why does the separate one-click pause and start control exclude SMB?
- Do Enterprise and Cloud include both documented forms of bulk task management?
keywords:
- bulk client task controls
- one-click task management
- edition client capabilities
- administrator task operations
legacy_ids:
- RS-FEAT-024
- RS-FEAT-187
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-024 | supports suspending all tasks, starting all tasks and deleting all tasks
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-187 | One click to manage all client tasks, can pause or start all tasks with one-click.
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions provide bulk client task controls?

## Short answer

The matrix has two distinct bulk-task entries. Suspending, starting, and deleting all tasks is documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. The separate one-click pause/start entry is SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

The ledger preserves an unresolved difference: RS-FEAT-024 lists suspend, start, and delete-all controls, while RS-FEAT-187 lists only one-click pause and start. The supplied evidence cannot select or confirm one complete bulk-action set. Verify the exact 8.1.8.7 edition and client UI before acting; do not assume that bulk deletion exists.

## Documented details

- Knowledge base ID: RS-FEAT-024
- Capability domain: Client App
- Original source text: supports suspending all tasks, starting all tasks and deleting all tasks
- Description: This entry describes the Raysync capability "supports suspending all tasks, starting all tasks and deleting all tasks." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 24
- Search keywords: Raysync, Client App, supports suspending all tasks, starting all tasks and deleting all tasks, SMB, Enterprise, Cloud, Multiple Spaces

- Knowledge base ID: RS-FEAT-187
- Capability domain: Advanced
- Original source text: One click to manage all client tasks, can pause or start all tasks with one-click.
- Description: This entry describes the Raysync capability "One click to manage all client tasks, can pause or start all tasks with one-click.." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 187
- Search keywords: Raysync, Advanced, One click to manage all client tasks, can pause or start all tasks with one-click., Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
