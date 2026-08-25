---
id: RSKB-TROUBLE-023
title: Respond to an Isolation Zone event
product: raysync
components:
- user-portal
- desktop-client
domain: troubleshooting
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
- What should I do after a transferred file enters the Isolation Zone?
- How can I tell whether antivirus or a sensitive word caused isolation?
- Which isolation evidence should I provide when a quarantined file needs review?
keywords:
- file isolated
- antivirus
- sensitive word
- Isolation Zone
- Why was my transferred file moved to the Isolation Zone?
- troubleshooting
- Raysync
legacy_ids:
- FAQ-TROUBLE-018
safety_tags:
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-018 | Why was my transferred file moved to the Isolation Zone?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Respond to an Isolation Zone event

## Short answer

Treat an isolated file as a security event. Stop retrying, renaming, repackaging, or redistributing it. This article covers response, evidence, and escalation only; the separate antivirus and sensitive-word guidance explains the possible causes.

## Likely cause

The file is no longer in the normal area because Raysync placed it in the Isolation Zone. Do not infer the specific trigger from the disappearance alone. Use the displayed isolation record to identify the documented reason.

## What the user can check

If your account can view the Isolation Zone, record the file name, displayed reason or virus information, isolation time, originating task, source and target locations, and account. Preserve the exact text or an approved screenshot. Do not download, restore, or manipulate the isolated item as a troubleshooting experiment.

## When to contact an administrator

Contact the administrator or security owner with the evidence and request authorized review. The end-user sources do not document self-service release or restoration from isolation, so do not assume that a retry or rename can clear the event.

## Version differences

Antivirus isolation is documented in both legacy and 8.1.8.0 and later guide families. Sensitive-word detection appears in the release history from version 6.5.8.0. The response remains evidence collection and administrator escalation in the available documentation.

## Important notes

Keep the isolated content contained until the authorized reviewer decides how it should be handled. Isolation protects users and data and is not a normal file-move state.
