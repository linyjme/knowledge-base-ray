---
id: RSKB-ADMIN-051
title: Are custom transfer notification email templates available, and in which editions?
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
- Can every edition customize the emails sent for transfer and antivirus events?
- Does SMB include custom notification templates for peer-to-peer transfers?
- Are storage-usage and group-library email templates customizable in Cloud?
keywords:
- custom transfer email templates
- event notification branding
- edition template availability
- administrator email customization
legacy_ids:
- RS-FEAT-191
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-191 | Email notification supports custom transfer email notification templates(Log In, Add Group file library, Upload and Download, Peer to Peer transfer, Storage usage reaches the specified percentage, Antivirus)
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Are custom transfer notification email templates available, and in which editions?

## Short answer

Custom transfer-notification email templates are documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. The listed scenarios include sign-in, group libraries, transfers, storage alerts, and antivirus events; a blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

## Documented details

- Knowledge base ID: RS-FEAT-191
- Capability domain: Advanced
- Original source text: Email notification supports custom transfer email notification templates(Log In, Add Group file library, Upload and Download, Peer to Peer transfer, Storage usage reaches the specified percentage, Antivirus)
- Description: The source lists login, adding a group file library, upload, download, peer-to-peer transfer, storage-usage alerts, and antivirus as notification scenarios. Version 8.1.8.6 added P2P transfer notifications and group-storage alerts.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.3; 8.1.8.6 - Added P2P transfer notifications and group storage alert notifications.
- Source location: Raysync Feature list.xlsx / English-New / row 191
- Search keywords: Raysync, Advanced, Email notification supports custom transfer email notification templates(Log In, Add Group file library, Upload and Download, Peer to Peer transfer, Storage usage reaches the specified percentage, Antivirus), SMB, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
