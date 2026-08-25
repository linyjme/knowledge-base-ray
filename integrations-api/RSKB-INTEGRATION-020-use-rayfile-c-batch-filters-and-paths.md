---
id: RSKB-INTEGRATION-020
title: 'Use rayfile-c batch filters and paths'
product: raysync
components:
- cli
- file-service
domain: integrations-api
access_level: support
audience:
- developer
- support-engineer
locale: en
applicable_versions:
  from: null
  to: null
version_status: uncertain
status: active
question_variants:
- 'How can I preview which objects a rayfile-c batch list and filters will select?'
- 'Which direct-file-client path option prevents a file-list transfer from flattening the destination tree?'
- 'Why should include and exclude behavior be tested on a small directory first?'
keywords:
- 'rayfile-c batch'
- 'file list'
- 'include exclude'
- 'target rename'
- 'full path'
- 'selection scope'
- 'direct file client'
- 'parameter validation'
- 'direct file client file list'
- 'preserve directory layout'
- 'flattened target tree'
legacy_ids: []
safety_tags:
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/rayfile-c-batch-filter-paths.md
  section: 'rayfile-c Batch list, filtering and path organization'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Use rayfile-c batch filters and paths

## Short answer

Choose one documented input method, validate list encoding and path roots, and test filters against a small known tree. Draw the expected destination layout before target renaming or full-path preservation so a broad selection cannot silently write outside the intended structure.

## Guidance

Treat the resolved object set as the exact target. Include and exclude cannot be used together; parameter validation must block submission when both are present. Record selected and skipped counts without exposing full paths. After execution, compare the expected and actual object lists, destination hierarchy, total size, failures, and representative checksums.

## Authorization and target

Only an authorized operator may act. Confirm the exact target service, identity, operation, source and destination, selected objects, conflict behavior, and expected result. Use placeholders such as `<host>`, `<token>`, and `<path>`; never put real credentials, endpoints, accounts, ports, identifiers, or full paths in documentation, command history, or support notes.

## Effect and confirmation

Confirm the file-list root, direct file client input method, one permitted filter family, target rename, and full-path behavior. The intended effect is the reviewed object set and destination hierarchy, not every object under a broader parent.

## Recovery boundary

Retain the source list and expected tree before transfer. If parameter validation, list decoding, or path-root checks disagree with the review, stop before submission. Restore overwritten targets only through the approved storage recovery path.

## Verification

Verify that the accepted source list equals the intended selection, then compare selected, skipped, failed, and delivered counts, destination hierarchy, target names, total size, representative checksums, and readability.
