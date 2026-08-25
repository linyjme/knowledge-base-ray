---
id: RSKB-INTEGRATION-015
title: 'HTTP download, preview, and WebSocket data-surface boundaries'
product: raysync
components:
- file-service
- http-api
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
- 'How does the file-service data surface differ from the manager HTTP control API?'
- 'Why can a preview failure coexist with a successful original-file transfer?'
- 'What should a caller verify when a negotiation response exposes old preview fields?'
keywords:
- 'HTTP download'
- 'file preview'
- 'WebSocket data'
- 'ZIP stream'
- 'binary frame'
- 'object identifier'
- 'local web API'
legacy_ids: []
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/http-preview.md
  section: 'HTTP download, preview and WebSocket'
  evidence_type: technical-boundary-document
- file: source_file/preview-range.md
  section: 'Preview failed or Range responded abnormally'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# HTTP download, preview, and WebSocket data-surface boundaries

## Short answer

Treat file download, preview, and file-service WebSocket data as a different surface from manager HTTP task control. Single files or directories stream through download behavior, multiple objects may use ZIP packaging, preview reads file content directly, and WebSocket data frames use binary mode.

## Guidance

Old negotiation fields do not prove that separate listeners exist; the runtime response and approved listening configuration provide the relevant evidence. A preview identifier remains short-lived and its canonical absolute path stays inside the allowed root. A preview failure does not by itself prove the original transfer failed.

For a Range failure, record the response status and requested byte interval, then verify that the object identifier is current, the canonical absolute path remains inside the allowed root, and the storage backend supports the required random read. These are diagnostic checks, not a general Range contract. This article does not guess TLS, ports, concurrency, shutdown behavior, or unsupported status semantics.

## Boundaries

This article is explanatory. It describes a documented data or result boundary and does not authorize changing a task, setting, listener, certificate, route, or remote object. Only the installed release's published contract is authoritative. Examples contain placeholders such as `<host>`, `<token>`, and `<path>`.
