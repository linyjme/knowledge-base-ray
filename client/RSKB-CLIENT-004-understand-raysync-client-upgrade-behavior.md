---
id: RSKB-CLIENT-004
title: Understand Raysync client upgrade behavior
product: raysync
components:
- user-portal
- desktop-client
- browser-plugin
domain: client
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
- Will my Raysync desktop client update silently or ask me first?
- Why did one client detect an upgrade while another installed it automatically?
- How can I tell which auto-update behavior applies to my deployment?
keywords:
- Auto upgrade desktop client
- automatic upgrade
- auto-update
- version
- default server
- silent upgrade
- Does the Raysync client upgrade automatically?
- client
legacy_ids:
- FAQ-CLIENT-010
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-018 | Auto upgrade desktop client
  evidence_type: feature-matrix
- file: raysync-user-faq/02-client-installation-and-settings.md
  section: FAQ-CLIENT-010 | Does the Raysync client upgrade automatically?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand Raysync client upgrade behavior

## Short answer

Two update behaviors are documented. With administrator-enabled auto-update, a correct default-server configuration, and a server version newer than the client version, the configuration guides say the client performs a silent upgrade. The cloud client guide separately says the client detects a new version and prompts the user to upgrade.

## Unresolved upgrade behavior

The approved sources document two behaviors: an administrator-enabled configuration can perform a silent upgrade, while the cloud-client guidance says the client detects a newer version and prompts the user. They do not establish which conditions choose between those behaviors, and this article does not select either behavior.

## Edition availability

Automatic desktop client upgrade is marked as supported for **SMB**, **Enterprise**, **Cloud**, and **Multiple Spaces**. That edition availability does not identify whether a particular deployment uses silent upgrade or a user prompt; it establishes capability availability, not the unresolved interaction behavior.

## Version differences

The supplied sources do not explain whether silent upgrade and detect-and-prompt apply to different client builds, settings, or deployment types, and they do not specify which behavior takes precedence when both conditions exist.

## Important notes

Keep the default-server connection correct. If an upgrade prompt appears, follow it; otherwise an enabled silent upgrade may require no action. To check manually, right-click the client, select **About**, view the client version, and check whether it is the latest Raysync version.
