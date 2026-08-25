---
title: "Raysync End-User FAQ Knowledge Base Guide"
product: "Raysync"
language: "en"
audience: "End user"
chunk_strategy: "Split at each level-three FAQ heading"
---

# Raysync End-User FAQ Knowledge Base Guide

## Purpose

This knowledge base answers product and workflow questions from ordinary Raysync end users. It covers getting started, login, client use, file operations, transfer tasks, synchronization, peer-to-peer transfer, share-download and invite-upload links, account settings, security, storage, group folders, troubleshooting, and version differences.

The content is organized for vector retrieval. Each level-three `FAQ-*` heading begins a self-contained answer that repeats the product, feature, user intent, version applicability, limitations, and source context needed by an answering agent.

## Audience: End user

The primary audience is a person using the Raysync user portal, desktop client, or browser plug-in. Administrator procedures are not reproduced unless an administrator prerequisite directly explains why an end-user feature is unavailable or behaves differently.

Examples of administrator prerequisites include enabling a feature, assigning a permission, configuring email, activating a license, or opening required network ports. When an FAQ contains such a prerequisite, the end user should contact a Raysync administrator rather than attempt an administrator procedure without authorization.

## Knowledge Base Categories

| ID prefix | Document | Scope |
|---|---|---|
| `START` | `01-getting-started-and-login.md` | Product introduction, portal access, login, logout, password recovery, and authentication choices. |
| `CLIENT` | `02-client-installation-and-settings.md` | Client download, installation, startup, upgrade, uninstall, transfer list, and client settings. |
| `FILE` | `03-file-upload-download-and-management.md` | Upload, download, preview, file management, personal/group files, recycle bin, and isolation behavior. |
| `TRANSFER` | `04-transfer-tasks.md` | General transfers, web/client modes, progress, pause, resume, verification, conflicts, and server-issued tasks. |
| `SYNC` | `05-file-synchronization.md` | Sync direction, frequency, filtering, conflicts, deletion, real-time sync, and task control. |
| `P2P` | `06-peer-to-peer-transfer.md` | P2P requirements, devices, sending, receiving, direct/relay modes, STUN, and legacy workflows. |
| `LINK` | `07-share-and-invite-links.md` | Share-download links, invite-upload links, recipient controls, email, limits, and link management. |
| `ACCOUNT` | `08-user-account-and-profile.md` | Personal information, passwords, email, spaces, permissions, and group membership. |
| `SECURITY` | `09-security-and-authentication.md` | TLS, 2FA, lockout, IP restrictions, antivirus, sensitive words, certificates, and external authentication. |
| `STORAGE` | `10-storage-and-group-folders.md` | Personal/group storage, permissions, quotas, virtual directories, spaces, and storage-related restrictions. |
| `TROUBLE` | `11-troubleshooting.md` | Symptom-led diagnosis for login, client, transfer, sync, P2P, links, permissions, and security. |
| `VERSION` | `12-version-differences.md` | User-visible workflow and capability changes across documented versions. |

## How to Interpret an FAQ

### Applies to

`Applies to` identifies the documented product version or version range for the primary answer. `All documented versions` means this knowledge base does not describe a material version difference for that answer. It does not claim compatibility with undocumented future versions.

### Version differences

`Version differences` records material historical behavior. When both current and legacy procedures exist, the current documented workflow appears first and the older workflow is labeled with its applicable version range.

The version-resolution order is:

1. The `Applies to` and `Version differences` fields in the current FAQ or RSKB article in this repository.
2. When those fields conflict across articles, prefer the more specific article for the user's feature and version.
3. A newer file timestamp alone does not establish a product-version boundary.

### Administrator prerequisite

An administrator prerequisite is a condition outside an ordinary user's permissions. The FAQ states the condition and tells the user when to contact an administrator, without turning the answer into an administrator configuration guide.

### Source uncertainty

If this knowledge base is blank, screenshot-only, ambiguous, or contradictory on a point, say that the available documentation does not specify the answer. Do not infer unsupported product behavior.

## Agent Answering Rules

1. Lead with the direct answer from `Short answer`.
2. Use the latest documented workflow by default.
3. Ask for the user's Raysync version only when the answer materially changes and the user did not provide a version.
4. If a version is unknown but clarification is unnecessary, give the current workflow first and add a concise legacy-version note.
5. Preserve port numbers, paths, limits, permissions, security warnings, overwrite behavior, source-deletion behavior, and other restrictions exactly.
6. State an administrator prerequisite in end-user language and explain when to contact the administrator.
7. Do not present share-download and invite-upload links as the same feature: a share-download link gives recipients access to download content; an invite-upload link allows recipients to upload content.
8. Do not treat screenshots as the only authority for a critical step.
9. Do not add generic troubleshooting actions that are absent from this knowledge base.
10. If this knowledge base does not specify an answer, say so directly.
11. Include an FAQ ID or article filename only when the platform supports citations or the user asks for verification.

## Retrieval and Chunking Guidance

- Split at each heading matching `### FAQ-[A-Z0-9]+-[0-9]{3} |`.
- Keep the complete FAQ block together through its `Sources` section.
- Do not split metadata from `Short answer`.
- Preserve numbered steps in their original order.
- Treat `Related questions` as navigation, not as part of the factual answer.
- Recommended retrieval is hybrid semantic and keyword search because exact terms such as version numbers, ports, device IDs, UI labels, and FAQ IDs benefit from lexical matching.

## Terminology

- **General transfer task:** A one-time upload or download task.
- **Sync task:** A task that synchronizes directories according to a direction and frequency.
- **Peer-to-peer transfer:** Direct or relayed file transfer between client devices.
- **Share-download link:** A link that allows a recipient to download shared content.
- **Invite-upload link:** A link that allows a recipient to upload content to a selected location.
- **User portal:** The web interface used by an ordinary Raysync user.
- **Desktop client:** The installed Raysync client application.
- **Browser plug-in:** The client component used for high-speed transfer through the web interface.

## Source Policy

This repository is the canonical knowledge base. Answer from the current articles and FAQ documents here. Do not retrieve, prefer, or cite an external source directory. In-article citations are for auditability and should not normally be quoted in an end-user answer.
