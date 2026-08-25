---
title: "Raysync Product Edition Feature Knowledge Base"
source: "Raysync Feature list.xlsx / worksheet: English-New / A1:G267"
language: "en"
schema_version: "1.0"
chunk_strategy: "Split by level-three heading (one RS-FEAT entry per chunk)"
editions: ["SMB", "Enterprise", "Cloud", "Multiple Spaces"]
---

# Raysync Product Edition Feature Knowledge Base

This knowledge base was compiled from the `English-New` worksheet in `Raysync Feature list.xlsx`. It covers the SMB, Enterprise, Cloud, and Multiple Spaces product editions and is designed for AI vector retrieval, edition comparison, presales Q&A, solution selection, and feature verification.

## Usage and Interpretation Rules

- `Supported`: represented by `√` in the source.
- `Not supported`: represented by `×` in the source.
- `Not specified in source`: the source cell is blank; support or non-support must not be inferred.
- Values such as `Unlimited`, `1 Gbps`, `10`, `License-controlled`, and `Starting from 2 TB` are quotas or licensing values, not simple support states.
- `Source version note`: taken from the note columns on the right side of the worksheet. It usually indicates the version in which a feature appeared or changed. When the source does not define the exact meaning, this knowledge base makes no additional inference.
- This knowledge base faithfully represents the workbook. It does not replace contracts, licenses, deployment requirements, or the latest official release notes. Answers should prioritize the applicable `RS-FEAT` entry.

## Product Edition Overview

| Edition | Explicitly supported | Explicitly unsupported | Quota/license value | Not specified |
|---|---:|---:|---:|---:|
| SMB | 165 | 70 | 5 | 1 |
| Enterprise | 228 | 8 | 5 | 0 |
| Cloud | 188 | 48 | 5 | 0 |
| Multiple Spaces | 222 | 14 | 1 | 4 |

> Counts cover detailed feature entries and exclude section headings. They provide a quick view of the matrix and do not represent pricing or commercial licensing terms.

### Core Capacity and Licensing Differences

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
|---|---|---|---|---|
| User account number | 10 | Unlimited | 10 | Not specified in source |
| TCP high-speed transfer | Unlimited | Unlimited | Unlimited | Not specified in source |
| UDP high-speed transfer | 1Gbps | License-controlled | 1Gbps | Not specified in source |
| Download volume | Unlimited | Unlimited | Starting from 2 TB | Not specified in source |

## Frequently Asked Questions

### How do account and transfer quotas differ across SMB, Enterprise, Cloud, and Multiple Spaces?

SMB: 10 accounts, unlimited TCP, 1 Gbps UDP, and unlimited download volume. Enterprise: unlimited accounts, unlimited TCP, license-controlled UDP, and unlimited download volume. Cloud: 10 accounts, unlimited TCP, 1 Gbps UDP, and download volume starting from 2 TB. Multiple Spaces is not specified for these four items in the source.

### Which editions support file synchronization?

Enterprise, Cloud, and Multiple Spaces support most file synchronization capabilities. SMB is marked as not supported for the synchronization entries. Real-time synchronization (upload only) is supported only by Enterprise and Cloud; Multiple Spaces does not support it.

### Which editions support peer-to-peer transfer?

Enterprise, Cloud, and Multiple Spaces support peer-to-peer transfer; SMB does not.

### Which editions support the command-line client and SDK?

Enterprise and Multiple Spaces support the operating systems listed for the command-line client and SDK. SMB and Cloud are both marked as not supported.

### Which capabilities are exclusive to Multiple Spaces?

Users joining multiple spaces, separate storage and permissions in different spaces, creating and assigning multiple spaces, space-level administrator permissions, space-level resources and configurations, and isolation of users, administrators, and data between spaces are all supported only by Multiple Spaces.

### What are the notable limitations of the Cloud edition?

In the source, Cloud does not support HTTP web file transfer, delivery tasks initiated from the admin portal, antivirus during file transfer, 2FA, sensitive-word detection, LDAP/AD and several external identity sources, group folders, clustered or high-availability deployment, the command-line client, the SDK, Syslog integration, and certain other capabilities. Retrieve the corresponding feature entry for an exact answer.

### Which Enterprise features require an additional payment?

Full-text retrieval of the file directory and online preview of CAD files are marked as supported for Enterprise, but their feature names explicitly state that an additional payment is required.

### Does a blank cell mean that a feature is not supported?

No. This knowledge base represents a blank cell as “Not specified in source.” Only an × in the source means “Not supported.”

## Capability Domain Navigation

- Common Capabilities (4 entries): Product-level quotas for accounts, transfer bandwidth, and download volume. Values in this domain may represent a numeric allowance or license control rather than simple support status.
- Network Transfer (1 entries): Automatic switching of Raysync high-speed protocols under different network conditions.
- File Management (6 entries): Management, search, preview, cleanup, and recycle-bin capabilities for personal and group files.
- Client App (9 entries): Desktop client login, upgrades, network diagnostics, logs, and task management.
- File Transfer (28 entries): High-speed transfer, resume, verification, encryption, compression, proxy, speed control, and task control.
- File Synchronization (21 entries): One-way and two-way synchronization, scheduled and real-time modes, change handling, conflict policies, filtering, and source-directory processing.
- Peer-to-Peer Transfer (7 entries): Direct sending and receiving between PCs, including offline and scheduled tasks.
- Delivery Tasks on Admin Portal (2 entries): Upload or delivery tasks initiated by an administrator between a client and server storage.
- External Links (21 entries): Invite-upload and share-download links, email notifications, access restrictions, and link security controls.
- Security (13 entries): Antivirus, IP policies, watermarks, SSL, password security, 2FA, sensitive-word detection, and certificates.
- User Management (28 entries): User roles, enterprise directories and identity sources, accounts, directories, permissions, speed limits, quotas, and space membership.
- Group Folders (13 entries): Group roles, member permissions, storage, speed limits, access paths, and file-filtering policies.
- Admin Management (9 entries): Multiple administrators, administrator roles, and space-level management and isolation in Multiple Spaces.
- Advanced (15 entries): Centralized management of monitoring, speed limits, databases, notifications, topology, and client policies.
- Server Scalability (1 entries): Server support for extensibility mechanisms such as file-event notifications.
- Storage (11 entries): Local storage, network file systems, public-cloud object storage, Ceph, and S3-compatible storage.
- Server Deployment (6 entries): Standalone, primary/standby, load-balanced, multi-port, and high-availability deployments.
- Customized Services (4 entries): Customization of web branding, clients, portal menus, and access entry points.
- Browser High-Speed Transfer Plug-in Supported Systems (6 entries): Operating systems supported by the browser high-speed transfer plug-in.
- Desktop Client Supported Systems (5 entries): Operating systems supported by the desktop client.
- Command Line Client Supported Systems (5 entries): Operating systems supported by the command-line client.
- SDK Supported Systems (5 entries): Operating systems on which the Raysync SDK can run or be integrated.
- Server Supported Systems (9 entries): Operating systems, architectures, and TLS capabilities supported by the Raysync server.
- Log Management (8 entries): System, user, administrator, sharing, and transfer logs, including Syslog integration and log collection.
- Data Statistics (4 entries): Statistics for storage, transfer volume, share links, and object storage.

## Detailed Feature Entries

## Common Capabilities

Product-level quotas for accounts, transfer bandwidth, and download volume. Values in this domain may represent a numeric allowance or license control rather than simple support status.

### RS-FEAT-003 | User account number

- Knowledge base ID: RS-FEAT-003
- Capability domain: Common Capabilities
- Original source text: User account number
- Description: SMB and Cloud are each marked for 10 accounts; Enterprise is marked Unlimited; Multiple Spaces does not specify an account limit.
- Edition availability: SMB: 10; Enterprise: Unlimited; Cloud: 10; Multiple Spaces: Not specified in source
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 3
- Search keywords: Raysync, Common Capabilities, User account number, SMB, Enterprise, Cloud

### RS-FEAT-004 | TCP high-speed transfer

- Knowledge base ID: RS-FEAT-004
- Capability domain: Common Capabilities
- Original source text: TCP high-speed transfer
- Description: TCP high-speed transfer is marked Unlimited for SMB, Enterprise, and Cloud; Multiple Spaces is not specified.
- Edition availability: SMB: Unlimited; Enterprise: Unlimited; Cloud: Unlimited; Multiple Spaces: Not specified in source
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 4
- Search keywords: Raysync, Common Capabilities, TCP high-speed transfer, SMB, Enterprise, Cloud

### RS-FEAT-005 | UDP high-speed transfer

- Knowledge base ID: RS-FEAT-005
- Capability domain: Common Capabilities
- Original source text: UDP high-speed transfer
- Description: SMB and Cloud are marked at 1 Gbps; Enterprise UDP bandwidth is controlled by the license; Multiple Spaces is not specified.
- Edition availability: SMB: 1Gbps; Enterprise: License-controlled; Cloud: 1Gbps; Multiple Spaces: Not specified in source
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 5
- Search keywords: Raysync, Common Capabilities, UDP high-speed transfer, SMB, Enterprise, Cloud

### RS-FEAT-006 | Download volume

- Knowledge base ID: RS-FEAT-006
- Capability domain: Common Capabilities
- Original source text: Download volume
- Description: Download volume is Unlimited for SMB and Enterprise; Cloud starts from 2 TB; Multiple Spaces is not specified.
- Edition availability: SMB: Unlimited; Enterprise: Unlimited; Cloud: Starting from 2 TB; Multiple Spaces: Not specified in source
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 6
- Search keywords: Raysync, Common Capabilities, Download volume, SMB, Enterprise, Cloud

## Network Transfer

Automatic switching of Raysync high-speed protocols under different network conditions.

### RS-FEAT-008 | Automatic switching of Raysync UDP and TCP protocol

- Knowledge base ID: RS-FEAT-008
- Capability domain: Network Transfer
- Original source text: Automatic switching of Raysync UDP and TCP protocol
- Description: This entry describes the Raysync capability “Automatic switching of Raysync UDP and TCP protocol.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 8
- Search keywords: Raysync, Network Transfer, Automatic switching of Raysync UDP and TCP protocol, SMB, Enterprise, Cloud, Multiple Spaces

## File Management

Management, search, preview, cleanup, and recycle-bin capabilities for personal and group files.

### RS-FEAT-010 | Support personal file management and group file management

- Knowledge base ID: RS-FEAT-010
- Capability domain: File Management
- Original source text: Support personal file management and group file management
- Description: This entry describes the Raysync capability “Support personal file management and group file management.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 10
- Search keywords: Raysync, File Management, Support personal file management and group file management, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-011 | Full-text retrieval of file directory (Additional paid for Enterprise)

- Knowledge base ID: RS-FEAT-011
- Capability domain: File Management
- Original source text: Full-text retrieval of file directory (Additional paid for Enterprise)
- Description: Enterprise is marked as supported, but the feature name explicitly states that an additional payment is required; SMB is not supported.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 11
- Search keywords: Raysync, File Management, Full-text retrieval of file directory (Additional paid for Enterprise), Enterprise, Cloud, Multiple Spaces

### RS-FEAT-012 | Support new folder, copy, move, rename, delete, Unzip

- Knowledge base ID: RS-FEAT-012
- Capability domain: File Management
- Original source text: Support new folder, copy, move, rename, delete, Unzip
- Description: This entry describes the Raysync capability “Support new folder, copy, move, rename, delete, Unzip.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 12
- Search keywords: Raysync, File Management, Support new folder, copy, move, rename, delete, Unzip, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-013 | Support online preview of files, pictures and videos

- Knowledge base ID: RS-FEAT-013
- Capability domain: File Management
- Original source text: Support online preview of files, pictures and videos
- Description: This entry describes the Raysync capability “Support online preview of files, pictures and videos.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 13
- Search keywords: Raysync, File Management, Support online preview of files, pictures and videos, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-014 | Support online preview of CAD file (Additional paid for Enterprise)

- Knowledge base ID: RS-FEAT-014
- Capability domain: File Management
- Original source text: Support online preview of CAD file (Additional paid for Enterprise)
- Description: Enterprise is marked as supported, but the feature name explicitly states that an additional payment is required; SMB is not supported.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 14
- Search keywords: Raysync, File Management, Support online preview of CAD file (Additional paid for Enterprise), Enterprise, Cloud, Multiple Spaces

### RS-FEAT-015 | Support expiration file cleaning and setting recycle bin path

- Knowledge base ID: RS-FEAT-015
- Capability domain: File Management
- Original source text: Support expiration file cleaning and setting recycle bin path
- Description: This entry describes the Raysync capability “Support expiration file cleaning and setting recycle bin path.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 15
- Search keywords: Raysync, File Management, Support expiration file cleaning and setting recycle bin path, SMB, Enterprise, Cloud, Multiple Spaces

## Client App

Desktop client login, upgrades, network diagnostics, logs, and task management.

### RS-FEAT-017 | Simultaneous login and access of single account and multiple terminals

- Knowledge base ID: RS-FEAT-017
- Capability domain: Client App
- Original source text: Simultaneous login and access of single account and multiple terminals
- Description: This entry describes the Raysync capability “Simultaneous login and access of single account and multiple terminals.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Unlimited; Enterprise: Unlimited; Cloud: Unlimited; Multiple Spaces: Unlimited
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 17
- Search keywords: Raysync, Client App, Simultaneous login and access of single account and multiple terminals, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-018 | Auto upgrade desktop client

- Knowledge base ID: RS-FEAT-018
- Capability domain: Client App
- Original source text: Auto upgrade desktop client
- Description: This entry describes the Raysync capability “Auto upgrade desktop client.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 18
- Search keywords: Raysync, Client App, Auto upgrade desktop client, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-019 | Automatically locate the cause of network connection failure, port detection

- Knowledge base ID: RS-FEAT-019
- Capability domain: Client App
- Original source text: Automatically locate the cause of network connection failure, port detection
- Description: This entry describes the Raysync capability “Automatically locate the cause of network connection failure, port detection.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 19
- Search keywords: Raysync, Client App, Automatically locate the cause of network connection failure, port detection, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-020 | UDP speed test

- Knowledge base ID: RS-FEAT-020
- Capability domain: Client App
- Original source text: UDP speed test
- Description: This entry describes the Raysync capability “UDP speed test.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.1
- Source location: Raysync Feature list.xlsx / English-New / row 20
- Search keywords: Raysync, Client App, UDP speed test, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-021 | Sorting client task priority

- Knowledge base ID: RS-FEAT-021
- Capability domain: Client App
- Original source text: Sorting client task priority
- Description: This entry describes the Raysync capability “Sorting client task priority.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 21
- Search keywords: Raysync, Client App, Sorting client task priority, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-022 | Collecting client logs

- Knowledge base ID: RS-FEAT-022
- Capability domain: Client App
- Original source text: Collecting client logs
- Description: This entry describes the Raysync capability “Collecting client logs.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.6.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 22
- Search keywords: Raysync, Client App, Collecting client logs, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-023 | Clean client logs and automatically compress logs

- Knowledge base ID: RS-FEAT-023
- Capability domain: Client App
- Original source text: Clean client logs and automatically compress logs
- Description: This entry describes the Raysync capability “Clean client logs and automatically compress logs.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.6.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 23
- Search keywords: Raysync, Client App, Clean client logs and automatically compress logs, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-024 | supports suspending all tasks, starting all tasks and deleting all tasks

- Knowledge base ID: RS-FEAT-024
- Capability domain: Client App
- Original source text: supports suspending all tasks, starting all tasks and deleting all tasks
- Description: This entry describes the Raysync capability “supports suspending all tasks, starting all tasks and deleting all tasks.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 24
- Search keywords: Raysync, Client App, supports suspending all tasks, starting all tasks and deleting all tasks, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-025 | Support for task sorting and filtering by creation time.

- Knowledge base ID: RS-FEAT-025
- Capability domain: Client App
- Original source text: Support for task sorting and filtering by creation time.
- Description: This entry describes the Raysync capability “Support for task sorting and filtering by creation time..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 8.1.8.6
- Source location: Raysync Feature list.xlsx / English-New / row 25
- Search keywords: Raysync, Client App, Support for task sorting and filtering by creation time., SMB, Enterprise, Cloud, Multiple Spaces

## File Transfer

High-speed transfer, resume, verification, encryption, compression, proxy, speed control, and task control.

### RS-FEAT-027 | Support file transfer with http web (support drag file and pause, cancel a task)

- Knowledge base ID: RS-FEAT-027
- Capability domain: File Transfer
- Original source text: Support file transfer with http web (support drag file and pause, cancel a task)
- Description: Cloud is explicitly marked as not supporting this web transfer method, while the other three editions support it.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.3.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 27
- Search keywords: Raysync, File Transfer, Support file transfer with http web (support drag file and pause, cancel a task), SMB, Enterprise, Multiple Spaces

### RS-FEAT-028 | Support high-speed transfer of millions of files in a single directory with UDP

- Knowledge base ID: RS-FEAT-028
- Capability domain: File Transfer
- Original source text: Support high-speed transfer of millions of files in a single directory with UDP
- Description: This entry describes the Raysync capability “Support high-speed transfer of millions of files in a single directory with UDP.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 28
- Search keywords: Raysync, File Transfer, Support high-speed transfer of millions of files in a single directory with UDP, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-029 | Support small file disk IO optimization

- Knowledge base ID: RS-FEAT-029
- Capability domain: File Transfer
- Original source text: Support small file disk IO optimization
- Description: This entry describes the Raysync capability “Support small file disk IO optimization.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 29
- Search keywords: Raysync, File Transfer, Support small file disk IO optimization, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-030 | Skip existing files at high speed during transfer

- Knowledge base ID: RS-FEAT-030
- Capability domain: File Transfer
- Original source text: Skip existing files at high speed during transfer
- Description: This entry describes the Raysync capability “Skip existing files at high speed during transfer.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 30
- Search keywords: Raysync, File Transfer, Skip existing files at high speed during transfer, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-031 | Supports skipping specified files during transfer

- Knowledge base ID: RS-FEAT-031
- Capability domain: File Transfer
- Original source text: Supports skipping specified files during transfer
- Description: This entry describes the Raysync capability “Supports skipping specified files during transfer.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 31
- Search keywords: Raysync, File Transfer, Supports skipping specified files during transfer, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-032 | Support skipping files over a specified size during transfer

- Knowledge base ID: RS-FEAT-032
- Capability domain: File Transfer
- Original source text: Support skipping files over a specified size during transfer
- Description: This entry describes the Raysync capability “Support skipping files over a specified size during transfer.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 32
- Search keywords: Raysync, File Transfer, Support skipping files over a specified size during transfer, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-033 | Support only upload or download new files

- Knowledge base ID: RS-FEAT-033
- Capability domain: File Transfer
- Original source text: Support only upload or download new files
- Description: This entry describes the Raysync capability “Support only upload or download new files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 33
- Search keywords: Raysync, File Transfer, Support only upload or download new files, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-034 | Support breakpoint resume in the process of file transfer

- Knowledge base ID: RS-FEAT-034
- Capability domain: File Transfer
- Original source text: Support breakpoint resume in the process of file transfer
- Description: This entry describes the Raysync capability “Support breakpoint resume in the process of file transfer.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 34
- Search keywords: Raysync, File Transfer, Support breakpoint resume in the process of file transfer, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-035 | File size and time automatic proofreading after the transfer is completed

- Knowledge base ID: RS-FEAT-035
- Capability domain: File Transfer
- Original source text: File size and time automatic proofreading after the transfer is completed
- Description: This entry describes the Raysync capability “File size and time automatic proofreading after the transfer is completed.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 35
- Search keywords: Raysync, File Transfer, File size and time automatic proofreading after the transfer is completed, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-036 | Hash automatic proofreading after the transfer is completed

- Knowledge base ID: RS-FEAT-036
- Capability domain: File Transfer
- Original source text: Hash automatic proofreading after the transfer is completed
- Description: This entry describes the Raysync capability “Hash automatic proofreading after the transfer is completed.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 36
- Search keywords: Raysync, File Transfer, Hash automatic proofreading after the transfer is completed, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-037 | Support TLS+AES-256 encryption algorithm

- Knowledge base ID: RS-FEAT-037
- Capability domain: File Transfer
- Original source text: Support TLS+AES-256 encryption algorithm
- Description: This entry describes the Raysync capability “Support TLS+AES-256 encryption algorithm.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 37
- Search keywords: Raysync, File Transfer, Support TLS+AES-256 encryption algorithm, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-038 | Support switching non-encrypted/encrypted mode

- Knowledge base ID: RS-FEAT-038
- Capability domain: File Transfer
- Original source text: Support switching non-encrypted/encrypted mode
- Description: This entry describes the Raysync capability “Support switching non-encrypted/encrypted mode.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 38
- Search keywords: Raysync, File Transfer, Support switching non-encrypted/encrypted mode, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-039 | Support for preserving file timestamps after transfer is completed

- Knowledge base ID: RS-FEAT-039
- Capability domain: File Transfer
- Original source text: Support for preserving file timestamps after transfer is completed
- Description: This entry describes the Raysync capability “Support for preserving file timestamps after transfer is completed.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 39
- Search keywords: Raysync, File Transfer, Support for preserving file timestamps after transfer is completed, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-040 | Automatic selection of compression scheme based on file type during transfer

- Knowledge base ID: RS-FEAT-040
- Capability domain: File Transfer
- Original source text: Automatic selection of compression scheme based on file type during transfer
- Description: This entry describes the Raysync capability “Automatic selection of compression scheme based on file type during transfer.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 40
- Search keywords: Raysync, File Transfer, Automatic selection of compression scheme based on file type during transfer, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-041 | Automatically update file owner and file owner's user group (Linux server only)

- Knowledge base ID: RS-FEAT-041
- Capability domain: File Transfer
- Original source text: Automatically update file owner and file owner's user group (Linux server only)
- Description: This entry describes the Raysync capability “Automatically update file owner and file owner's user group (Linux server only).” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 41
- Search keywords: Raysync, File Transfer, Automatically update file owner and file owner's user group (Linux server only), SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-042 | Support Rsync algorithm to upload and download files

- Knowledge base ID: RS-FEAT-042
- Capability domain: File Transfer
- Original source text: Support Rsync algorithm to upload and download files
- Description: This entry describes the Raysync capability “Support Rsync algorithm to upload and download files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 42
- Search keywords: Raysync, File Transfer, Support Rsync algorithm to upload and download files, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-043 | Supports specifying the maximum number of upload and download tasks

- Knowledge base ID: RS-FEAT-043
- Capability domain: File Transfer
- Original source text: Supports specifying the maximum number of upload and download tasks
- Description: This entry describes the Raysync capability “Supports specifying the maximum number of upload and download tasks.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 43
- Search keywords: Raysync, File Transfer, Supports specifying the maximum number of upload and download tasks, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-044 | Support limit upload and download maximum and minimum speed

- Knowledge base ID: RS-FEAT-044
- Capability domain: File Transfer
- Original source text: Support limit upload and download maximum and minimum speed
- Description: This entry describes the Raysync capability “Support limit upload and download maximum and minimum speed.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 44
- Search keywords: Raysync, File Transfer, Support limit upload and download maximum and minimum speed, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-045 | Supports specify the number of files in parallel for a task

- Knowledge base ID: RS-FEAT-045
- Capability domain: File Transfer
- Original source text: Supports specify the number of files in parallel for a task
- Description: This entry describes the Raysync capability “Supports specify the number of files in parallel for a task.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 45
- Search keywords: Raysync, File Transfer, Supports specify the number of files in parallel for a task, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-046 | Support SOCKS5 proxy

- Knowledge base ID: RS-FEAT-046
- Capability domain: File Transfer
- Original source text: Support SOCKS5 proxy
- Description: This entry describes the Raysync capability “Support SOCKS5 proxy.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 46
- Search keywords: Raysync, File Transfer, Support SOCKS5 proxy, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-047 | Support setting Default server

- Knowledge base ID: RS-FEAT-047
- Capability domain: File Transfer
- Original source text: Support setting Default server
- Description: This entry describes the Raysync capability “Support setting Default server.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 47
- Search keywords: Raysync, File Transfer, Support setting Default server, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-048 | Support rename file when the targe file already exists

- Knowledge base ID: RS-FEAT-048
- Capability domain: File Transfer
- Original source text: Support rename file when the targe file already exists
- Description: This entry describes the Raysync capability “Support rename file when the targe file already exists.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 48
- Search keywords: Raysync, File Transfer, Support rename file when the targe file already exists, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-049 | Support Check before transfer

- Knowledge base ID: RS-FEAT-049
- Capability domain: File Transfer
- Original source text: Support Check before transfer
- Description: This entry describes the Raysync capability “Support Check before transfer.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 49
- Search keywords: Raysync, File Transfer, Support Check before transfer, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-050 | Support file ACL attribute (it can be preserve on the same system)

- Knowledge base ID: RS-FEAT-050
- Capability domain: File Transfer
- Original source text: Support file ACL attribute (it can be preserve on the same system)
- Description: This entry describes the Raysync capability “Support file ACL attribute (it can be preserve on the same system).” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 50
- Search keywords: Raysync, File Transfer, Support file ACL attribute (it can be preserve on the same system), SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-051 | Reserve the complete structure of the source directory when uploading to the target

- Knowledge base ID: RS-FEAT-051
- Capability domain: File Transfer
- Original source text: Reserve the complete structure of the source directory when uploading to the target
- Description: This entry describes the Raysync capability “Reserve the complete structure of the source directory when uploading to the target.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 51
- Search keywords: Raysync, File Transfer, Reserve the complete structure of the source directory when uploading to the target, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-052 | Support for long task queues.

- Knowledge base ID: RS-FEAT-052
- Capability domain: File Transfer
- Original source text: Support for long task queues.
- Description: This entry describes the Raysync capability “Support for long task queues..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 8.1.8.6
- Source location: Raysync Feature list.xlsx / English-New / row 52
- Search keywords: Raysync, File Transfer, Support for long task queues., SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-053 | Support for multi‑channel transfer.

- Knowledge base ID: RS-FEAT-053
- Capability domain: File Transfer
- Original source text: Support for multi‑channel transfer.
- Description: This entry describes the Raysync capability “Support for multi‑channel transfer..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 8.1.8.6
- Source location: Raysync Feature list.xlsx / English-New / row 53
- Search keywords: Raysync, File Transfer, Support for multi‑channel transfer., SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-054 | Support for GSO (Generic Segmentation Offload).

- Knowledge base ID: RS-FEAT-054
- Capability domain: File Transfer
- Original source text: Support for GSO (Generic Segmentation Offload).
- Description: This entry describes the Raysync capability “Support for GSO (Generic Segmentation Offload)..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 8.1.8.6
- Source location: Raysync Feature list.xlsx / English-New / row 54
- Search keywords: Raysync, File Transfer, Support for GSO (Generic Segmentation Offload)., SMB, Enterprise, Cloud, Multiple Spaces

## File Synchronization

One-way and two-way synchronization, scheduled and real-time modes, change handling, conflict policies, filtering, and source-directory processing.

### RS-FEAT-056 | Setting sync frequency

- Knowledge base ID: RS-FEAT-056
- Capability domain: File Synchronization
- Original source text: Setting sync frequency
- Description: This entry describes the Raysync capability “Setting sync frequency.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 56
- Search keywords: Raysync, File Synchronization, Setting sync frequency, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-057 | Unidirectional and bidirectional synchronization

- Knowledge base ID: RS-FEAT-057
- Capability domain: File Synchronization
- Original source text: Unidirectional and bidirectional synchronization
- Description: This entry describes the Raysync capability “Unidirectional and bidirectional synchronization.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 57
- Search keywords: Raysync, File Synchronization, Unidirectional and bidirectional synchronization, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-058 | Aadd files/folders synchronously

- Knowledge base ID: RS-FEAT-058
- Capability domain: File Synchronization
- Original source text: Aadd files/folders synchronously
- Description: This entry describes the Raysync capability “Aadd files/folders synchronously.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 58
- Search keywords: Raysync, File Synchronization, Aadd files/folders synchronously, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-059 | Delete files/folders synchronously

- Knowledge base ID: RS-FEAT-059
- Capability domain: File Synchronization
- Original source text: Delete files/folders synchronously
- Description: This entry describes the Raysync capability “Delete files/folders synchronously.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 59
- Search keywords: Raysync, File Synchronization, Delete files/folders synchronously, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-060 | Deleting source files after synchronization complete (Delete al the source directorys and file )

- Knowledge base ID: RS-FEAT-060
- Capability domain: File Synchronization
- Original source text: Deleting source files after synchronization complete (Delete al the source directorys and file )
- Description: This entry describes the Raysync capability “Deleting source files after synchronization complete (Delete al the source directorys and file ).” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 60
- Search keywords: Raysync, File Synchronization, Deleting source files after synchronization complete (Delete al the source directorys and file ), Enterprise, Cloud, Multiple Spaces

### RS-FEAT-061 | Deleting source files after synchronization complete (Reserve source directory structure)

- Knowledge base ID: RS-FEAT-061
- Capability domain: File Synchronization
- Original source text: Deleting source files after synchronization complete (Reserve source directory structure)
- Description: This entry describes the Raysync capability “Deleting source files after synchronization complete (Reserve source directory structure).” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 61
- Search keywords: Raysync, File Synchronization, Deleting source files after synchronization complete (Reserve source directory structure), Enterprise, Cloud, Multiple Spaces

### RS-FEAT-062 | Preserve directory structure when deleting source files

- Knowledge base ID: RS-FEAT-062
- Capability domain: File Synchronization
- Original source text: Preserve directory structure when deleting source files
- Description: This entry describes the Raysync capability “Preserve directory structure when deleting source files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.6.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 62
- Search keywords: Raysync, File Synchronization, Preserve directory structure when deleting source files, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-063 | Transfer only files and folders in the source directory

- Knowledge base ID: RS-FEAT-063
- Capability domain: File Synchronization
- Original source text: Transfer only files and folders in the source directory
- Description: This entry describes the Raysync capability “Transfer only files and folders in the source directory.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 63
- Search keywords: Raysync, File Synchronization, Transfer only files and folders in the source directory, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-064 | Preserve file modification time

- Knowledge base ID: RS-FEAT-064
- Capability domain: File Synchronization
- Original source text: Preserve file modification time
- Description: This entry describes the Raysync capability “Preserve file modification time.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 64
- Search keywords: Raysync, File Synchronization, Preserve file modification time, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-065 | Overwriting existing files

- Knowledge base ID: RS-FEAT-065
- Capability domain: File Synchronization
- Original source text: Overwriting existing files
- Description: This entry describes the Raysync capability “Overwriting existing files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 65
- Search keywords: Raysync, File Synchronization, Overwriting existing files, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-066 | Appending existing files

- Knowledge base ID: RS-FEAT-066
- Capability domain: File Synchronization
- Original source text: Appending existing files
- Description: This entry describes the Raysync capability “Appending existing files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 66
- Search keywords: Raysync, File Synchronization, Appending existing files, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-067 | Rename when file exists

- Knowledge base ID: RS-FEAT-067
- Capability domain: File Synchronization
- Original source text: Rename when file exists
- Description: This entry describes the Raysync capability “Rename when file exists.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.3.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 67
- Search keywords: Raysync, File Synchronization, Rename when file exists, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-068 | Overwrite when the source file is newer

- Knowledge base ID: RS-FEAT-068
- Capability domain: File Synchronization
- Original source text: Overwrite when the source file is newer
- Description: This entry describes the Raysync capability “Overwrite when the source file is newer.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.3.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 68
- Search keywords: Raysync, File Synchronization, Overwrite when the source file is newer, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-069 | Filtering of specified files

- Knowledge base ID: RS-FEAT-069
- Capability domain: File Synchronization
- Original source text: Filtering of specified files
- Description: This entry describes the Raysync capability “Filtering of specified files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 69
- Search keywords: Raysync, File Synchronization, Filtering of specified files, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-070 | Support for synchronizing multiple source directories

- Knowledge base ID: RS-FEAT-070
- Capability domain: File Synchronization
- Original source text: Support for synchronizing multiple source directories
- Description: This entry describes the Raysync capability “Support for synchronizing multiple source directories.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 70
- Search keywords: Raysync, File Synchronization, Support for synchronizing multiple source directories, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-071 | Support Check before transfer

- Knowledge base ID: RS-FEAT-071
- Capability domain: File Synchronization
- Original source text: Support Check before transfer
- Description: This entry describes the Raysync capability “Support Check before transfer.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.7.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 71
- Search keywords: Raysync, File Synchronization, Support Check before transfer, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-072 | Support file ACL attribute (it can be preserve on the same system)

- Knowledge base ID: RS-FEAT-072
- Capability domain: File Synchronization
- Original source text: Support file ACL attribute (it can be preserve on the same system)
- Description: This entry describes the Raysync capability “Support file ACL attribute (it can be preserve on the same system).” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.7.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 72
- Search keywords: Raysync, File Synchronization, Support file ACL attribute (it can be preserve on the same system), Enterprise, Cloud, Multiple Spaces

### RS-FEAT-073 | After synchronization is completed, the source files are moved and deleted

- Knowledge base ID: RS-FEAT-073
- Capability domain: File Synchronization
- Original source text: After synchronization is completed, the source files are moved and deleted
- Description: This entry describes the Raysync capability “After synchronization is completed, the source files are moved and deleted.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 73
- Search keywords: Raysync, File Synchronization, After synchronization is completed, the source files are moved and deleted, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-074 | Reserve the complete structure of the source directory when uploading to the target

- Knowledge base ID: RS-FEAT-074
- Capability domain: File Synchronization
- Original source text: Reserve the complete structure of the source directory when uploading to the target
- Description: This entry describes the Raysync capability “Reserve the complete structure of the source directory when uploading to the target.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.7.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 74
- Search keywords: Raysync, File Synchronization, Reserve the complete structure of the source directory when uploading to the target, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-075 | Synchronize when source files are updated

- Knowledge base ID: RS-FEAT-075
- Capability domain: File Synchronization
- Original source text: Synchronize when source files are updated
- Description: This entry describes the Raysync capability “Synchronize when source files are updated.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.6.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 75
- Search keywords: Raysync, File Synchronization, Synchronize when source files are updated, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-076 | Supports real-time sync (Upload only)

- Knowledge base ID: RS-FEAT-076
- Capability domain: File Synchronization
- Original source text: Supports real-time sync (Upload only)
- Description: Real-time synchronization is upload-only. Enterprise and Cloud support it; SMB and Multiple Spaces do not.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: Enterprise, Cloud
- Explicitly unsupported editions: SMB, Multiple Spaces
- Source version note: 8.1.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 76
- Search keywords: Raysync, File Synchronization, Supports real-time sync (Upload only), Enterprise, Cloud

## Peer-to-Peer Transfer

Direct sending and receiving between PCs, including offline and scheduled tasks.

### RS-FEAT-078 | Support point-to-point transmission on PC

- Knowledge base ID: RS-FEAT-078
- Capability domain: Peer-to-Peer Transfer
- Original source text: Support point-to-point transmission on PC
- Description: This entry describes the Raysync capability “Support point-to-point transmission on PC.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 78
- Search keywords: Raysync, Peer-to-Peer Transfer, Support point-to-point transmission on PC, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-079 | Support update device ID

- Knowledge base ID: RS-FEAT-079
- Capability domain: Peer-to-Peer Transfer
- Original source text: Support update device ID
- Description: This entry describes the Raysync capability “Support update device ID.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 79
- Search keywords: Raysync, Peer-to-Peer Transfer, Support update device ID, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-080 | Support for setting the path for receiving files

- Knowledge base ID: RS-FEAT-080
- Capability domain: Peer-to-Peer Transfer
- Original source text: Support for setting the path for receiving files
- Description: This entry describes the Raysync capability “Support for setting the path for receiving files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 80
- Search keywords: Raysync, Peer-to-Peer Transfer, Support for setting the path for receiving files, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-081 | Support for closing peer-to-peer file reception

- Knowledge base ID: RS-FEAT-081
- Capability domain: Peer-to-Peer Transfer
- Original source text: Support for closing peer-to-peer file reception
- Description: This entry describes the Raysync capability “Support for closing peer-to-peer file reception.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 81
- Search keywords: Raysync, Peer-to-Peer Transfer, Support for closing peer-to-peer file reception, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-082 | Supports sending offline tasks

- Knowledge base ID: RS-FEAT-082
- Capability domain: Peer-to-Peer Transfer
- Original source text: Supports sending offline tasks
- Description: This entry describes the Raysync capability “Supports sending offline tasks.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.8.8.1
- Source location: Raysync Feature list.xlsx / English-New / row 82
- Search keywords: Raysync, Peer-to-Peer Transfer, Supports sending offline tasks, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-083 | Supports moving from source path to target path

- Knowledge base ID: RS-FEAT-083
- Capability domain: Peer-to-Peer Transfer
- Original source text: Supports moving from source path to target path
- Description: This entry describes the Raysync capability “Supports moving from source path to target path.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 83
- Search keywords: Raysync, Peer-to-Peer Transfer, Supports moving from source path to target path, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-084 | Support scheduled sending

- Knowledge base ID: RS-FEAT-084
- Capability domain: Peer-to-Peer Transfer
- Original source text: Support scheduled sending
- Description: This entry describes the Raysync capability “Support scheduled sending.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 84
- Search keywords: Raysync, Peer-to-Peer Transfer, Support scheduled sending, Enterprise, Cloud, Multiple Spaces

## Delivery Tasks on Admin Portal

Upload or delivery tasks initiated by an administrator between a client and server storage.

### RS-FEAT-086 | Support creating upload tasks from client local to server storage on the admin portal

- Knowledge base ID: RS-FEAT-086
- Capability domain: Delivery Tasks on Admin Portal
- Original source text: Support creating upload tasks from client local to server storage on the admin portal
- Description: This entry describes the Raysync capability “Support creating upload tasks from client local to server storage on the admin portal.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: 6.4.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 86
- Search keywords: Raysync, Delivery Tasks on Admin Portal, Support creating upload tasks from client local to server storage on the admin portal, Enterprise, Multiple Spaces

### RS-FEAT-087 | Support creating delivery tasks from server storage to client local on the admin portal

- Knowledge base ID: RS-FEAT-087
- Capability domain: Delivery Tasks on Admin Portal
- Original source text: Support creating delivery tasks from server storage to client local on the admin portal
- Description: This entry describes the Raysync capability “Support creating delivery tasks from server storage to client local on the admin portal.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: 6.4.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 87
- Search keywords: Raysync, Delivery Tasks on Admin Portal, Support creating delivery tasks from server storage to client local on the admin portal, Enterprise, Multiple Spaces

## External Links

Invite-upload and share-download links, email notifications, access restrictions, and link security controls.

### RS-FEAT-089 | Create link to invite upload files

- Knowledge base ID: RS-FEAT-089
- Capability domain: External Links
- Original source text: Create link to invite upload files
- Description: This entry describes the Raysync capability “Create link to invite upload files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 89
- Search keywords: Raysync, External Links, Create link to invite upload files, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-090 | Creat link to share download files

- Knowledge base ID: RS-FEAT-090
- Capability domain: External Links
- Original source text: Creat link to share download files
- Description: This entry describes the Raysync capability “Creat link to share download files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 90
- Search keywords: Raysync, External Links, Creat link to share download files, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-091 | Setting file aliases when generating shared download links

- Knowledge base ID: RS-FEAT-091
- Capability domain: External Links
- Original source text: Setting file aliases when generating shared download links
- Description: This entry describes the Raysync capability “Setting file aliases when generating shared download links.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 91
- Search keywords: Raysync, External Links, Setting file aliases when generating shared download links, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-092 | Setting the expiration date of the external link password

- Knowledge base ID: RS-FEAT-092
- Capability domain: External Links
- Original source text: Setting the expiration date of the external link password
- Description: This entry describes the Raysync capability “Setting the expiration date of the external link password.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 92
- Search keywords: Raysync, External Links, Setting the expiration date of the external link password, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-093 | Send share/invite link automatically via mail

- Knowledge base ID: RS-FEAT-093
- Capability domain: External Links
- Original source text: Send share/invite link automatically via mail
- Description: This entry describes the Raysync capability “Send share/invite link automatically via mail.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 93
- Search keywords: Raysync, External Links, Send share/invite link automatically via mail, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-094 | Send mail notification when upload start or complete

- Knowledge base ID: RS-FEAT-094
- Capability domain: External Links
- Original source text: Send mail notification when upload start or complete
- Description: This entry describes the Raysync capability “Send mail notification when upload start or complete.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 94
- Search keywords: Raysync, External Links, Send mail notification when upload start or complete, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-095 | Send mail notification when download start or complete

- Knowledge base ID: RS-FEAT-095
- Capability domain: External Links
- Original source text: Send mail notification when download start or complete
- Description: This entry describes the Raysync capability “Send mail notification when download start or complete.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 95
- Search keywords: Raysync, External Links, Send mail notification when download start or complete, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-096 | Link and password email are sent separately

- Knowledge base ID: RS-FEAT-096
- Capability domain: External Links
- Original source text: Link and password email are sent separately
- Description: This entry describes the Raysync capability “Link and password email are sent separately.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 96
- Search keywords: Raysync, External Links, Link and password email are sent separately, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-097 | Support download links to bind the first device

- Knowledge base ID: RS-FEAT-097
- Capability domain: External Links
- Original source text: Support download links to bind the first device
- Description: This entry describes the Raysync capability “Support download links to bind the first device.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 97
- Search keywords: Raysync, External Links, Support download links to bind the first device, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-098 | View records such as the number of shared downloads and IPs

- Knowledge base ID: RS-FEAT-098
- Capability domain: External Links
- Original source text: View records such as the number of shared downloads and IPs
- Description: This entry describes the Raysync capability “View records such as the number of shared downloads and IPs.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 98
- Search keywords: Raysync, External Links, View records such as the number of shared downloads and IPs, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-099 | Support for sharing or inviting internal members

- Knowledge base ID: RS-FEAT-099
- Capability domain: External Links
- Original source text: Support for sharing or inviting internal members
- Description: This entry describes the Raysync capability “Support for sharing or inviting internal members.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 99
- Search keywords: Raysync, External Links, Support for sharing or inviting internal members, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-100 | Sharing supports limited download times

- Knowledge base ID: RS-FEAT-100
- Capability domain: External Links
- Original source text: Sharing supports limited download times
- Description: This entry describes the Raysync capability “Sharing supports limited download times.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 100
- Search keywords: Raysync, External Links, Sharing supports limited download times, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-101 | Sharing supports scheduled sending

- Knowledge base ID: RS-FEAT-101
- Capability domain: External Links
- Original source text: Sharing supports scheduled sending
- Description: This entry describes the Raysync capability “Sharing supports scheduled sending.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 101
- Search keywords: Raysync, External Links, Sharing supports scheduled sending, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-102 | Add deletion permission to invitation upload

- Knowledge base ID: RS-FEAT-102
- Capability domain: External Links
- Original source text: Add deletion permission to invitation upload
- Description: This entry describes the Raysync capability “Add deletion permission to invitation upload.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 102
- Search keywords: Raysync, External Links, Add deletion permission to invitation upload, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-103 | Share or invite internal members

- Knowledge base ID: RS-FEAT-103
- Capability domain: External Links
- Original source text: Share or invite internal members
- Description: This entry describes the Raysync capability “Share or invite internal members.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 103
- Search keywords: Raysync, External Links, Share or invite internal members, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-104 | Share download supports limiting the number of downloads

- Knowledge base ID: RS-FEAT-104
- Capability domain: External Links
- Original source text: Share download supports limiting the number of downloads
- Description: This entry describes the Raysync capability “Share download supports limiting the number of downloads.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 104
- Search keywords: Raysync, External Links, Share download supports limiting the number of downloads, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-105 | Share download support scheduled sending

- Knowledge base ID: RS-FEAT-105
- Capability domain: External Links
- Original source text: Share download support scheduled sending
- Description: This entry describes the Raysync capability “Share download support scheduled sending.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 105
- Search keywords: Raysync, External Links, Share download support scheduled sending, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-106 | Added deletion permission for invitation upload

- Knowledge base ID: RS-FEAT-106
- Capability domain: External Links
- Original source text: Added deletion permission for invitation upload
- Description: This entry describes the Raysync capability “Added deletion permission for invitation upload.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 106
- Search keywords: Raysync, External Links, Added deletion permission for invitation upload, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-107 | Sharing and invitation support notifications to private recipients

- Knowledge base ID: RS-FEAT-107
- Capability domain: External Links
- Original source text: Sharing and invitation support notifications to private recipients
- Description: This entry describes the Raysync capability “Sharing and invitation support notifications to private recipients.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 107
- Search keywords: Raysync, External Links, Sharing and invitation support notifications to private recipients, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-108 | Sharing and inviting support access with a specified email address

- Knowledge base ID: RS-FEAT-108
- Capability domain: External Links
- Original source text: Sharing and inviting support access with a specified email address
- Description: This entry describes the Raysync capability “Sharing and inviting support access with a specified email address.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 108
- Search keywords: Raysync, External Links, Sharing and inviting support access with a specified email address, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-109 | Enabling and disabling external links

- Knowledge base ID: RS-FEAT-109
- Capability domain: External Links
- Original source text: Enabling and disabling external links
- Description: This entry describes the Raysync capability “Enabling and disabling external links.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise, Cloud
- Explicitly unsupported editions: Multiple Spaces
- Source version note: 8.1.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 109
- Search keywords: Raysync, External Links, Enabling and disabling external links, SMB, Enterprise, Cloud

## Security

Antivirus, IP policies, watermarks, SSL, password security, 2FA, sensitive-word detection, and certificates.

### RS-FEAT-111 | Antivirus during file transfer

- Knowledge base ID: RS-FEAT-111
- Capability domain: Security
- Original source text: Antivirus during file transfer
- Description: This entry describes the Raysync capability “Antivirus during file transfer.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 111
- Search keywords: Raysync, Security, Antivirus during file transfer, Enterprise, Multiple Spaces

### RS-FEAT-112 | Set the IP black and white list for space access

- Knowledge base ID: RS-FEAT-112
- Capability domain: Security
- Original source text: Set the IP black and white list for space access
- Description: This entry describes the Raysync capability “Set the IP black and white list for space access.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 112
- Search keywords: Raysync, Security, Set the IP black and white list for space access, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-113 | IP black and white list for login

- Knowledge base ID: RS-FEAT-113
- Capability domain: Security
- Original source text: IP black and white list for login
- Description: This entry describes the Raysync capability “IP black and white list for login.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 113
- Search keywords: Raysync, Security, IP black and white list for login, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-114 | Set video playback watermark

- Knowledge base ID: RS-FEAT-114
- Capability domain: Security
- Original source text: Set video playback watermark
- Description: This entry describes the Raysync capability “Set video playback watermark.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 114
- Search keywords: Raysync, Security, Set video playback watermark, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-115 | Upload server certificate to enable encrypted web access via domain name.

- Knowledge base ID: RS-FEAT-115
- Capability domain: Security
- Original source text: Upload server certificate to enable encrypted web access via domain name.
- Description: This entry describes the Raysync capability “Upload server certificate to enable encrypted web access via domain name..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 115
- Search keywords: Raysync, Security, Upload server certificate to enable encrypted web access via domain name., SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-116 | Prohibit non-SSL security connection

- Knowledge base ID: RS-FEAT-116
- Capability domain: Security
- Original source text: Prohibit non-SSL security connection
- Description: This entry describes the Raysync capability “Prohibit non-SSL security connection.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 116
- Search keywords: Raysync, Security, Prohibit non-SSL security connection, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-117 | Password locking, for example, if a user enters an incorrect password for all five attempts, the account will be locked

- Knowledge base ID: RS-FEAT-117
- Capability domain: Security
- Original source text: Password locking, for example, if a user enters an incorrect password for all five attempts, the account will be locked
- Description: This entry describes the Raysync capability “Password locking, for example, if a user enters an incorrect password for all five attempts, the account will be locked.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 117
- Search keywords: Raysync, Security, Password locking, for example, if a user enters an incorrect password for all five attempts, the account will be locked, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-118 | Administrator can set weak password dictionary, the password in the dictionary does not allow user to set

- Knowledge base ID: RS-FEAT-118
- Capability domain: Security
- Original source text: Administrator can set weak password dictionary, the password in the dictionary does not allow user to set
- Description: This entry describes the Raysync capability “Administrator can set weak password dictionary, the password in the dictionary does not allow user to set.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 118
- Search keywords: Raysync, Security, Administrator can set weak password dictionary, the password in the dictionary does not allow user to set, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-119 | Support 2FA login verification for both users and administrators(Email,Authenticator App)

- Knowledge base ID: RS-FEAT-119
- Capability domain: Security
- Original source text: Support 2FA login verification for both users and administrators(Email,Authenticator App)
- Description: The source version note also states that version 8.1.8.6 added Authenticator App support for administrators. Cloud is marked as not supported.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.4.8.0; 8.1.8.6（administrator, add Authenticator App）
- Source location: Raysync Feature list.xlsx / English-New / row 119
- Search keywords: Raysync, Security, Support 2FA login verification for both users and administrators(Email,Authenticator App), SMB, Enterprise, Multiple Spaces

### RS-FEAT-120 | Users can log in without email verification

- Knowledge base ID: RS-FEAT-120
- Capability domain: Security
- Original source text: Users can log in without email verification
- Description: This entry describes the Raysync capability “Users can log in without email verification.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 120
- Search keywords: Raysync, Security, Users can log in without email verification, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-121 | Support sensitive word detection

- Knowledge base ID: RS-FEAT-121
- Capability domain: Security
- Original source text: Support sensitive word detection
- Description: This entry describes the Raysync capability “Support sensitive word detection.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 121
- Search keywords: Raysync, Security, Support sensitive word detection, Enterprise, Multiple Spaces

### RS-FEAT-122 | Malicious IP Login Restriction Policy

- Knowledge base ID: RS-FEAT-122
- Capability domain: Security
- Original source text: Malicious IP Login Restriction Policy
- Description: This entry describes the Raysync capability “Malicious IP Login Restriction Policy.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise, Cloud
- Explicitly unsupported editions: Multiple Spaces
- Source version note: 8.1.8.4
- Source location: Raysync Feature list.xlsx / English-New / row 122
- Search keywords: Raysync, Security, Malicious IP Login Restriction Policy, SMB, Enterprise, Cloud

### RS-FEAT-123 | Support for custom client certificates.

- Knowledge base ID: RS-FEAT-123
- Capability domain: Security
- Original source text: Support for custom client certificates.
- Description: This entry describes the Raysync capability “Support for custom client certificates..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 8.1.8.6
- Source location: Raysync Feature list.xlsx / English-New / row 123
- Search keywords: Raysync, Security, Support for custom client certificates., SMB, Enterprise, Cloud, Multiple Spaces

## User Management

User roles, enterprise directories and identity sources, accounts, directories, permissions, speed limits, quotas, and space membership.

### RS-FEAT-125 | Support user roles, set permissions for roles, and associate users

- Knowledge base ID: RS-FEAT-125
- Capability domain: User Management
- Original source text: Support user roles, set permissions for roles, and associate users
- Description: This entry describes the Raysync capability “Support user roles, set permissions for roles, and associate users.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 125
- Search keywords: Raysync, User Management, Support user roles, set permissions for roles, and associate users, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-126 | Connection to LDAP/AD domain user server and import the users (department/email/name/employee number) and groups of the AD domain

- Knowledge base ID: RS-FEAT-126
- Capability domain: User Management
- Original source text: Connection to LDAP/AD domain user server and import the users (department/email/name/employee number) and groups of the AD domain
- Description: Enterprise supports LDAP/AD. Cloud and Multiple Spaces do not. The SMB cell is blank, so support or non-support must not be inferred.
- Edition availability: SMB: Not specified in source; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Explicitly supported editions: Enterprise
- Explicitly unsupported editions: Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 126
- Search keywords: Raysync, User Management, Connection to LDAP/AD domain user server and import the users (department/email/name/employee number) and groups of the AD domain, Enterprise

### RS-FEAT-127 | Connection to mailbox server, can use the existing mailbox account as the transfer system account

- Knowledge base ID: RS-FEAT-127
- Capability domain: User Management
- Original source text: Connection to mailbox server, can use the existing mailbox account as the transfer system account
- Description: This entry describes the Raysync capability “Connection to mailbox server, can use the existing mailbox account as the transfer system account.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Explicitly supported editions: Enterprise
- Explicitly unsupported editions: SMB, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 127
- Search keywords: Raysync, User Management, Connection to mailbox server, can use the existing mailbox account as the transfer system account, Enterprise

### RS-FEAT-128 | Support OpenID Connect authentication

- Knowledge base ID: RS-FEAT-128
- Capability domain: User Management
- Original source text: Support OpenID Connect authentication
- Description: This entry describes the Raysync capability “Support OpenID Connect authentication.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Explicitly supported editions: Enterprise
- Explicitly unsupported editions: SMB, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 128
- Search keywords: Raysync, User Management, Support OpenID Connect authentication, Enterprise

### RS-FEAT-129 | Support authentication by server operating system user (Linux server version only)

- Knowledge base ID: RS-FEAT-129
- Capability domain: User Management
- Original source text: Support authentication by server operating system user (Linux server version only)
- Description: This entry describes the Raysync capability “Support authentication by server operating system user (Linux server version only).” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Explicitly supported editions: Enterprise
- Explicitly unsupported editions: SMB, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 129
- Search keywords: Raysync, User Management, Support authentication by server operating system user (Linux server version only), Enterprise

### RS-FEAT-130 | User system customization connection with Http interface

- Knowledge base ID: RS-FEAT-130
- Capability domain: User Management
- Original source text: User system customization connection with Http interface
- Description: This entry describes the Raysync capability “User system customization connection with Http interface.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Explicitly supported editions: Enterprise
- Explicitly unsupported editions: SMB, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 130
- Search keywords: Raysync, User Management, User system customization connection with Http interface, Enterprise

### RS-FEAT-131 | Copy accounts

- Knowledge base ID: RS-FEAT-131
- Capability domain: User Management
- Original source text: Copy accounts
- Description: This entry describes the Raysync capability “Copy accounts.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise, Cloud
- Explicitly unsupported editions: Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 131
- Search keywords: Raysync, User Management, Copy accounts, SMB, Enterprise, Cloud

### RS-FEAT-132 | Import and export accounts in bulk

- Knowledge base ID: RS-FEAT-132
- Capability domain: User Management
- Original source text: Import and export accounts in bulk
- Description: This entry describes the Raysync capability “Import and export accounts in bulk.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise, Cloud
- Explicitly unsupported editions: Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 132
- Search keywords: Raysync, User Management, Import and export accounts in bulk, SMB, Enterprise, Cloud

### RS-FEAT-133 | Set user file management permissions

- Knowledge base ID: RS-FEAT-133
- Capability domain: User Management
- Original source text: Set user file management permissions
- Description: This entry describes the Raysync capability “Set user file management permissions.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 133
- Search keywords: Raysync, User Management, Set user file management permissions, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-134 | User transfer speed settings

- Knowledge base ID: RS-FEAT-134
- Capability domain: User Management
- Original source text: User transfer speed settings
- Description: This entry describes the Raysync capability “User transfer speed settings.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 134
- Search keywords: Raysync, User Management, User transfer speed settings, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-135 | Allow users to upload new files only

- Knowledge base ID: RS-FEAT-135
- Capability domain: User Management
- Original source text: Allow users to upload new files only
- Description: This entry describes the Raysync capability “Allow users to upload new files only.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 135
- Search keywords: Raysync, User Management, Allow users to upload new files only, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-136 | Blacklist or whitelist of user transfer file formats

- Knowledge base ID: RS-FEAT-136
- Capability domain: User Management
- Original source text: Blacklist or whitelist of user transfer file formats
- Description: This entry describes the Raysync capability “Blacklist or whitelist of user transfer file formats.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 136
- Search keywords: Raysync, User Management, Blacklist or whitelist of user transfer file formats, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-137 | Set user transfer file filtering conditions

- Knowledge base ID: RS-FEAT-137
- Capability domain: User Management
- Original source text: Set user transfer file filtering conditions
- Description: This entry describes the Raysync capability “Set user transfer file filtering conditions.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 137
- Search keywords: Raysync, User Management, Set user transfer file filtering conditions, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-138 | Custom user's home directory storage space, and support multiple virtual directories

- Knowledge base ID: RS-FEAT-138
- Capability domain: User Management
- Original source text: Custom user's home directory storage space, and support multiple virtual directories
- Description: This entry describes the Raysync capability “Custom user's home directory storage space, and support multiple virtual directories.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 138
- Search keywords: Raysync, User Management, Custom user's home directory storage space, and support multiple virtual directories, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-139 | Set the user's forbidden access path, support wildcards

- Knowledge base ID: RS-FEAT-139
- Capability domain: User Management
- Original source text: Set the user's forbidden access path, support wildcards
- Description: This entry describes the Raysync capability “Set the user's forbidden access path, support wildcards.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 139
- Search keywords: Raysync, User Management, Set the user's forbidden access path, support wildcards, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-140 | Set the user's allowed access path, support wildcards

- Knowledge base ID: RS-FEAT-140
- Capability domain: User Management
- Original source text: Set the user's allowed access path, support wildcards
- Description: This entry describes the Raysync capability “Set the user's allowed access path, support wildcards.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 140
- Search keywords: Raysync, User Management, Set the user's allowed access path, support wildcards, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-141 | Set notification email sender

- Knowledge base ID: RS-FEAT-141
- Capability domain: User Management
- Original source text: Set notification email sender
- Description: This entry describes the Raysync capability “Set notification email sender.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 141
- Search keywords: Raysync, User Management, Set notification email sender, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-142 | Support not showing hidden files

- Knowledge base ID: RS-FEAT-142
- Capability domain: User Management
- Original source text: Support not showing hidden files
- Description: This entry describes the Raysync capability “Support not showing hidden files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 142
- Search keywords: Raysync, User Management, Support not showing hidden files, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-143 | Support department

- Knowledge base ID: RS-FEAT-143
- Capability domain: User Management
- Original source text: Support department
- Description: This entry describes the Raysync capability “Support department.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise, Cloud
- Explicitly unsupported editions: Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 143
- Search keywords: Raysync, User Management, Support department, SMB, Enterprise, Cloud

### RS-FEAT-144 | Specify to enable/disable the p2p function for users

- Knowledge base ID: RS-FEAT-144
- Capability domain: User Management
- Original source text: Specify to enable/disable the p2p function for users
- Description: This entry describes the Raysync capability “Specify to enable/disable the p2p function for users.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 144
- Search keywords: Raysync, User Management, Specify to enable/disable the p2p function for users, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-145 | AD domain supports scheduled account and group synchronization

- Knowledge base ID: RS-FEAT-145
- Capability domain: User Management
- Original source text: AD domain supports scheduled account and group synchronization
- Description: This entry describes the Raysync capability “AD domain supports scheduled account and group synchronization.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise, Cloud
- Explicitly unsupported editions: Multiple Spaces
- Source version note: 6.8.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 145
- Search keywords: Raysync, User Management, AD domain supports scheduled account and group synchronization, SMB, Enterprise, Cloud

### RS-FEAT-146 | Regularly clean or move home directory files

- Knowledge base ID: RS-FEAT-146
- Capability domain: User Management
- Original source text: Regularly clean or move home directory files
- Description: This entry describes the Raysync capability “Regularly clean or move home directory files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.1
- Source location: Raysync Feature list.xlsx / English-New / row 146
- Search keywords: Raysync, User Management, Regularly clean or move home directory files, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-147 | Account validity period settings

- Knowledge base ID: RS-FEAT-147
- Capability domain: User Management
- Original source text: Account validity period settings
- Description: This entry describes the Raysync capability “Account validity period settings.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.1
- Source location: Raysync Feature list.xlsx / English-New / row 147
- Search keywords: Raysync, User Management, Account validity period settings, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-148 | Create account email notification

- Knowledge base ID: RS-FEAT-148
- Capability domain: User Management
- Original source text: Create account email notification
- Description: This entry describes the Raysync capability “Create account email notification.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.1
- Source location: Raysync Feature list.xlsx / English-New / row 148
- Search keywords: Raysync, User Management, Create account email notification, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-149 | Maximum storage limit for Personal files

- Knowledge base ID: RS-FEAT-149
- Capability domain: User Management
- Original source text: Maximum storage limit for Personal files
- Description: This entry describes the Raysync capability “Maximum storage limit for Personal files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 149
- Search keywords: Raysync, User Management, Maximum storage limit for Personal files, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-150 | Users can join multiple Spaces

- Knowledge base ID: RS-FEAT-150
- Capability domain: User Management
- Original source text: Users can join multiple Spaces
- Description: This capability is exclusive to Multiple Spaces; the other three editions are all marked as not supported.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 150
- Search keywords: Raysync, User Management, Users can join multiple Spaces, Multiple Spaces

### RS-FEAT-151 | Users have different storage and permissions in different Spaces.

- Knowledge base ID: RS-FEAT-151
- Capability domain: User Management
- Original source text: Users have different storage and permissions in different Spaces.
- Description: This capability is exclusive to Multiple Spaces and provides separate storage and permissions for the same user in different spaces.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 151
- Search keywords: Raysync, User Management, Users have different storage and permissions in different Spaces., Multiple Spaces

### RS-FEAT-152 | Support for user transfer priorities.

- Knowledge base ID: RS-FEAT-152
- Capability domain: User Management
- Original source text: Support for user transfer priorities.
- Description: This entry describes the Raysync capability “Support for user transfer priorities..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 8.1.8.6
- Source location: Raysync Feature list.xlsx / English-New / row 152
- Search keywords: Raysync, User Management, Support for user transfer priorities., SMB, Enterprise, Cloud, Multiple Spaces

## Group Folders

Group roles, member permissions, storage, speed limits, access paths, and file-filtering policies.

### RS-FEAT-154 | Support group roles and set group role permissions

- Knowledge base ID: RS-FEAT-154
- Capability domain: Group Folders
- Original source text: Support group roles and set group role permissions
- Description: This entry describes the Raysync capability “Support group roles and set group role permissions.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 154
- Search keywords: Raysync, Group Folders, Support group roles and set group role permissions, SMB, Enterprise, Multiple Spaces

### RS-FEAT-155 | Set group folder permission of members

- Knowledge base ID: RS-FEAT-155
- Capability domain: Group Folders
- Original source text: Set group folder permission of members
- Description: This entry describes the Raysync capability “Set group folder permission of members.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 155
- Search keywords: Raysync, Group Folders, Set group folder permission of members, SMB, Enterprise, Multiple Spaces

### RS-FEAT-156 | Support adding administrators to the group folder

- Knowledge base ID: RS-FEAT-156
- Capability domain: Group Folders
- Original source text: Support adding administrators to the group folder
- Description: This entry describes the Raysync capability “Support adding administrators to the group folder.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.4.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 156
- Search keywords: Raysync, Group Folders, Support adding administrators to the group folder, SMB, Enterprise, Multiple Spaces

### RS-FEAT-157 | Set the storage space of the group folder, and support the configuration of multiple virtual directories

- Knowledge base ID: RS-FEAT-157
- Capability domain: Group Folders
- Original source text: Set the storage space of the group folder, and support the configuration of multiple virtual directories
- Description: This entry describes the Raysync capability “Set the storage space of the group folder, and support the configuration of multiple virtual directories.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 157
- Search keywords: Raysync, Group Folders, Set the storage space of the group folder, and support the configuration of multiple virtual directories, SMB, Enterprise, Multiple Spaces

### RS-FEAT-158 | Set group folder associated user transfer speed

- Knowledge base ID: RS-FEAT-158
- Capability domain: Group Folders
- Original source text: Set group folder associated user transfer speed
- Description: This entry describes the Raysync capability “Set group folder associated user transfer speed.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 158
- Search keywords: Raysync, Group Folders, Set group folder associated user transfer speed, SMB, Enterprise, Multiple Spaces

### RS-FEAT-159 | Can set the associated user to upload new files only

- Knowledge base ID: RS-FEAT-159
- Capability domain: Group Folders
- Original source text: Can set the associated user to upload new files only
- Description: This entry describes the Raysync capability “Can set the associated user to upload new files only.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 159
- Search keywords: Raysync, Group Folders, Can set the associated user to upload new files only, SMB, Enterprise, Multiple Spaces

### RS-FEAT-160 | Set file filter conditions for associated user

- Knowledge base ID: RS-FEAT-160
- Capability domain: Group Folders
- Original source text: Set file filter conditions for associated user
- Description: This entry describes the Raysync capability “Set file filter conditions for associated user.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 160
- Search keywords: Raysync, Group Folders, Set file filter conditions for associated user, SMB, Enterprise, Multiple Spaces

### RS-FEAT-161 | Skip files over set size when transferring

- Knowledge base ID: RS-FEAT-161
- Capability domain: Group Folders
- Original source text: Skip files over set size when transferring
- Description: This entry describes the Raysync capability “Skip files over set size when transferring.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 161
- Search keywords: Raysync, Group Folders, Skip files over set size when transferring, SMB, Enterprise, Multiple Spaces

### RS-FEAT-162 | Support setting speed limit

- Knowledge base ID: RS-FEAT-162
- Capability domain: Group Folders
- Original source text: Support setting speed limit
- Description: This entry describes the Raysync capability “Support setting speed limit.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 162
- Search keywords: Raysync, Group Folders, Support setting speed limit, SMB, Enterprise, Multiple Spaces

### RS-FEAT-163 | Support setting forbidden access paths and allowed access paths

- Knowledge base ID: RS-FEAT-163
- Capability domain: Group Folders
- Original source text: Support setting forbidden access paths and allowed access paths
- Description: This entry describes the Raysync capability “Support setting forbidden access paths and allowed access paths.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 163
- Search keywords: Raysync, Group Folders, Support setting forbidden access paths and allowed access paths, SMB, Enterprise, Multiple Spaces

### RS-FEAT-164 | Support setting maximum storage capacity

- Knowledge base ID: RS-FEAT-164
- Capability domain: Group Folders
- Original source text: Support setting maximum storage capacity
- Description: This entry describes the Raysync capability “Support setting maximum storage capacity.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 164
- Search keywords: Raysync, Group Folders, Support setting maximum storage capacity, SMB, Enterprise, Multiple Spaces

### RS-FEAT-165 | Black/white list of uploaded file formats

- Knowledge base ID: RS-FEAT-165
- Capability domain: Group Folders
- Original source text: Black/white list of uploaded file formats
- Description: This entry describes the Raysync capability “Black/white list of uploaded file formats.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.8.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 165
- Search keywords: Raysync, Group Folders, Black/white list of uploaded file formats, SMB, Enterprise, Multiple Spaces

### RS-FEAT-166 | Maximum storage limit for Group files

- Knowledge base ID: RS-FEAT-166
- Capability domain: Group Folders
- Original source text: Maximum storage limit for Group files
- Description: This entry describes the Raysync capability “Maximum storage limit for Group files.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 166
- Search keywords: Raysync, Group Folders, Maximum storage limit for Group files, SMB, Enterprise, Multiple Spaces

## Admin Management

Multiple administrators, administrator roles, and space-level management and isolation in Multiple Spaces.

### RS-FEAT-168 | Create multiple administrators

- Knowledge base ID: RS-FEAT-168
- Capability domain: Admin Management
- Original source text: Create multiple administrators
- Description: This entry describes the Raysync capability “Create multiple administrators.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.8
- Source location: Raysync Feature list.xlsx / English-New / row 168
- Search keywords: Raysync, Admin Management, Create multiple administrators, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-169 | Support admin roles, set permissions for roles, and associate admin

- Knowledge base ID: RS-FEAT-169
- Capability domain: Admin Management
- Original source text: Support admin roles, set permissions for roles, and associate admin
- Description: This entry describes the Raysync capability “Support admin roles, set permissions for roles, and associate admin.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.8
- Source location: Raysync Feature list.xlsx / English-New / row 169
- Search keywords: Raysync, Admin Management, Support admin roles, set permissions for roles, and associate admin, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-170 | Supports creating multiple spaces and assigning them to administrators

- Knowledge base ID: RS-FEAT-170
- Capability domain: Admin Management
- Original source text: Supports creating multiple spaces and assigning them to administrators
- Description: This is a space-management capability exclusive to Multiple Spaces.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: 6.8.8.8
- Source location: Raysync Feature list.xlsx / English-New / row 170
- Search keywords: Raysync, Admin Management, Supports creating multiple spaces and assigning them to administrators, Multiple Spaces

### RS-FEAT-171 | Administrators can manage multiple spaces, administrators can only view the administrators, users, configurations, logs, etc. of their assigned space.

- Knowledge base ID: RS-FEAT-171
- Capability domain: Admin Management
- Original source text: Administrators can manage multiple spaces, administrators can only view the administrators, users, configurations, logs, etc. of their assigned space.
- Description: This capability is exclusive to Multiple Spaces. Administrators can view only the objects and configurations in their assigned spaces.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: 6.8.8.8
- Source location: Raysync Feature list.xlsx / English-New / row 171
- Search keywords: Raysync, Admin Management, Administrators can manage multiple spaces, administrators can only view the administrators, users, configurations, logs, etc. of their assigned space., Multiple Spaces

### RS-FEAT-172 | Administrators have different permissions in different spaces

- Knowledge base ID: RS-FEAT-172
- Capability domain: Admin Management
- Original source text: Administrators have different permissions in different spaces
- Description: This is the space-level administrator permission model exclusive to Multiple Spaces.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: 6.8.8.8
- Source location: Raysync Feature list.xlsx / English-New / row 172
- Search keywords: Raysync, Admin Management, Administrators have different permissions in different spaces, Multiple Spaces

### RS-FEAT-173 | Supports create storages, administrators, users, groups in different spaces

- Knowledge base ID: RS-FEAT-173
- Capability domain: Admin Management
- Original source text: Supports create storages, administrators, users, groups in different spaces
- Description: This capability is exclusive to Multiple Spaces and allows storage, administrators, users, and groups to be created separately in each space.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: 6.8.8.8
- Source location: Raysync Feature list.xlsx / English-New / row 173
- Search keywords: Raysync, Admin Management, Supports create storages, administrators, users, groups in different spaces, Multiple Spaces

### RS-FEAT-174 | Different Spaces support different space configuration

- Knowledge base ID: RS-FEAT-174
- Capability domain: Admin Management
- Original source text: Different Spaces support different space configuration
- Description: This capability is exclusive to Multiple Spaces; each space can use a different configuration.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: 6.8.8.8
- Source location: Raysync Feature list.xlsx / English-New / row 174
- Search keywords: Raysync, Admin Management, Different Spaces support different space configuration, Multiple Spaces

### RS-FEAT-175 | Users, administrators and data in different Spaces are isolated

- Knowledge base ID: RS-FEAT-175
- Capability domain: Admin Management
- Original source text: Users, administrators and data in different Spaces are isolated
- Description: This capability is exclusive to Multiple Spaces; users, administrators, and data are isolated between spaces.
- Edition availability: SMB: Not supported; Enterprise: Not supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Multiple Spaces
- Explicitly unsupported editions: SMB, Enterprise, Cloud
- Source version note: 6.8.8.8
- Source location: Raysync Feature list.xlsx / English-New / row 175
- Search keywords: Raysync, Admin Management, Users, administrators and data in different Spaces are isolated, Multiple Spaces

### RS-FEAT-176 | Support for OIDC authentication login.

- Knowledge base ID: RS-FEAT-176
- Capability domain: Admin Management
- Original source text: Support for OIDC authentication login.
- Description: This entry describes the Raysync capability “Support for OIDC authentication login..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 8.1.8.6
- Source location: Raysync Feature list.xlsx / English-New / row 176
- Search keywords: Raysync, Admin Management, Support for OIDC authentication login., SMB, Enterprise, Cloud, Multiple Spaces

## Advanced

Centralized management of monitoring, speed limits, databases, notifications, topology, and client policies.

### RS-FEAT-178 | Server real-time monitoring

- Knowledge base ID: RS-FEAT-178
- Capability domain: Advanced
- Original source text: Server real-time monitoring
- Description: This entry describes the Raysync capability “Server real-time monitoring.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 178
- Search keywords: Raysync, Advanced, Server real-time monitoring, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-179 | Custom maximum speed time period

- Knowledge base ID: RS-FEAT-179
- Capability domain: Advanced
- Original source text: Custom maximum speed time period
- Description: This entry describes the Raysync capability “Custom maximum speed time period.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 179
- Search keywords: Raysync, Advanced, Custom maximum speed time period, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-180 | Custom transfer units

- Knowledge base ID: RS-FEAT-180
- Capability domain: Advanced
- Original source text: Custom transfer units
- Description: This entry describes the Raysync capability “Custom transfer units.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 180
- Search keywords: Raysync, Advanced, Custom transfer units, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-181 | Can set the limited transfer speed to less than 1M

- Knowledge base ID: RS-FEAT-181
- Capability domain: Advanced
- Original source text: Can set the limited transfer speed to less than 1M
- Description: This entry describes the Raysync capability “Can set the limited transfer speed to less than 1M.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.4.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 181
- Search keywords: Raysync, Advanced, Can set the limited transfer speed to less than 1M, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-182 | Blacklist or whitelist of transfer file formats

- Knowledge base ID: RS-FEAT-182
- Capability domain: Advanced
- Original source text: Blacklist or whitelist of transfer file formats
- Description: This entry describes the Raysync capability “Blacklist or whitelist of transfer file formats.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 182
- Search keywords: Raysync, Advanced, Blacklist or whitelist of transfer file formats, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-183 | Server built-in small database (Sqlite)

- Knowledge base ID: RS-FEAT-183
- Capability domain: Advanced
- Original source text: Server built-in small database (Sqlite)
- Description: This entry describes the Raysync capability “Server built-in small database (Sqlite).” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 183
- Search keywords: Raysync, Advanced, Server built-in small database (Sqlite), SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-184 | Connection with external database (MySQL), so that multiple Raysync servers share the database in load balancing mode

- Knowledge base ID: RS-FEAT-184
- Capability domain: Advanced
- Original source text: Connection with external database (MySQL), so that multiple Raysync servers share the database in load balancing mode
- Description: This entry describes the Raysync capability “Connection with external database (MySQL), so that multiple Raysync servers share the database in load balancing mode.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 184
- Search keywords: Raysync, Advanced, Connection with external database (MySQL), so that multiple Raysync servers share the database in load balancing mode, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-185 | Set statistics period

- Knowledge base ID: RS-FEAT-185
- Capability domain: Advanced
- Original source text: Set statistics period
- Description: This entry describes the Raysync capability “Set statistics period.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 185
- Search keywords: Raysync, Advanced, Set statistics period, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-186 | Support custom notifications and system notifications

- Knowledge base ID: RS-FEAT-186
- Capability domain: Advanced
- Original source text: Support custom notifications and system notifications
- Description: This entry describes the Raysync capability “Support custom notifications and system notifications.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.4.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 186
- Search keywords: Raysync, Advanced, Support custom notifications and system notifications, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-187 | One click to manage all client tasks, can pause or start all tasks with one-click.

- Knowledge base ID: RS-FEAT-187
- Capability domain: Advanced
- Original source text: One click to manage all client tasks, can pause or start all tasks with one-click.
- Description: This entry describes the Raysync capability “One click to manage all client tasks, can pause or start all tasks with one-click..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 187
- Search keywords: Raysync, Advanced, One click to manage all client tasks, can pause or start all tasks with one-click., Enterprise, Cloud, Multiple Spaces

### RS-FEAT-188 | Support real-time network topology map

- Knowledge base ID: RS-FEAT-188
- Capability domain: Advanced
- Original source text: Support real-time network topology map
- Description: This entry describes the Raysync capability “Support real-time network topology map.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.4.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 188
- Search keywords: Raysync, Advanced, Support real-time network topology map, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-189 | Support forcibly enable/disable client hash, encryption, rsync settings

- Knowledge base ID: RS-FEAT-189
- Capability domain: Advanced
- Original source text: Support forcibly enable/disable client hash, encryption, rsync settings
- Description: This entry describes the Raysync capability “Support forcibly enable/disable client hash, encryption, rsync settings.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.6.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 189
- Search keywords: Raysync, Advanced, Support forcibly enable/disable client hash, encryption, rsync settings, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-190 | Support setting client transfer task name

- Knowledge base ID: RS-FEAT-190
- Capability domain: Advanced
- Original source text: Support setting client transfer task name
- Description: This entry describes the Raysync capability “Support setting client transfer task name.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 190
- Search keywords: Raysync, Advanced, Support setting client transfer task name, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-191 | Email notification supports custom transfer email notification templates(Log In, Add Group file library, Upload and Download, Peer to Peer transfer, Storage usage reaches the specified percentage, Antivirus)

- Knowledge base ID: RS-FEAT-191
- Capability domain: Advanced
- Original source text: Email notification supports custom transfer email notification templates(Log In, Add Group file library, Upload and Download, Peer to Peer transfer, Storage usage reaches the specified percentage, Antivirus)
- Description: The source lists login, adding a group file library, upload, download, peer-to-peer transfer, storage-usage alerts, and antivirus as notification scenarios. Version 8.1.8.6 added P2P transfer notifications and group-storage alerts.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.3; 8.1.8.6 – Added P2P transfer notifications and group storage alert notifications.
- Source location: Raysync Feature list.xlsx / English-New / row 191
- Search keywords: Raysync, Advanced, Email notification supports custom transfer email notification templates(Log In, Add Group file library, Upload and Download, Peer to Peer transfer, Storage usage reaches the specified percentage, Antivirus), SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-192 | Supports disabling and enabling sync tasks in the admin portal

- Knowledge base ID: RS-FEAT-192
- Capability domain: Advanced
- Original source text: Supports disabling and enabling sync tasks in the admin portal
- Description: This entry describes the Raysync capability “Supports disabling and enabling sync tasks in the admin portal.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 192
- Search keywords: Raysync, Advanced, Supports disabling and enabling sync tasks in the admin portal, SMB, Enterprise, Cloud, Multiple Spaces

## Server Scalability

Server support for extensibility mechanisms such as file-event notifications.

### RS-FEAT-194 | Notification of file events

- Knowledge base ID: RS-FEAT-194
- Capability domain: Server Scalability
- Original source text: Notification of file events
- Description: This entry describes the Raysync capability “Notification of file events.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 194
- Search keywords: Raysync, Server Scalability, Notification of file events, SMB, Enterprise, Cloud, Multiple Spaces

## Storage

Local storage, network file systems, public-cloud object storage, Ceph, and S3-compatible storage.

### RS-FEAT-196 | Local disk file system

- Knowledge base ID: RS-FEAT-196
- Capability domain: Storage
- Original source text: Local disk file system
- Description: This entry describes the Raysync capability “Local disk file system.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 196
- Search keywords: Raysync, Storage, Local disk file system, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-197 | Network file systems (systems such as NFS/SMB mounted as server directories or drive letter)

- Knowledge base ID: RS-FEAT-197
- Capability domain: Storage
- Original source text: Network file systems (systems such as NFS/SMB mounted as server directories or drive letter)
- Description: This entry describes the Raysync capability “Network file systems (systems such as NFS/SMB mounted as server directories or drive letter).” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 197
- Search keywords: Raysync, Storage, Network file systems (systems such as NFS/SMB mounted as server directories or drive letter), SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-198 | Wasabi

- Knowledge base ID: RS-FEAT-198
- Capability domain: Storage
- Original source text: Wasabi
- Description: This entry describes the Raysync capability “Wasabi.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 198
- Search keywords: Raysync, Storage, Wasabi, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-199 | Backblaze

- Knowledge base ID: RS-FEAT-199
- Capability domain: Storage
- Original source text: Backblaze
- Description: This entry describes the Raysync capability “Backblaze.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 199
- Search keywords: Raysync, Storage, Backblaze, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-200 | AWS S3

- Knowledge base ID: RS-FEAT-200
- Capability domain: Storage
- Original source text: AWS S3
- Description: This entry describes the Raysync capability “AWS S3.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 200
- Search keywords: Raysync, Storage, AWS S3, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-201 | Azure Blob

- Knowledge base ID: RS-FEAT-201
- Capability domain: Storage
- Original source text: Azure Blob
- Description: This entry describes the Raysync capability “Azure Blob.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 201
- Search keywords: Raysync, Storage, Azure Blob, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-202 | Google cloud storage

- Knowledge base ID: RS-FEAT-202
- Capability domain: Storage
- Original source text: Google cloud storage
- Description: This entry describes the Raysync capability “Google cloud storage.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 202
- Search keywords: Raysync, Storage, Google cloud storage, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-203 | Tencent COS

- Knowledge base ID: RS-FEAT-203
- Capability domain: Storage
- Original source text: Tencent COS
- Description: This entry describes the Raysync capability “Tencent COS.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 203
- Search keywords: Raysync, Storage, Tencent COS, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-204 | MinIO

- Knowledge base ID: RS-FEAT-204
- Capability domain: Storage
- Original source text: MinIO
- Description: This entry describes the Raysync capability “MinIO.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 204
- Search keywords: Raysync, Storage, MinIO, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-205 | Ceph-class object storage like DigitalOcean/Linode/Vultr, and support Ceph object storage built by themselves (users need to configure Cephde S3 object gateway)

- Knowledge base ID: RS-FEAT-205
- Capability domain: Storage
- Original source text: Ceph-class object storage like DigitalOcean/Linode/Vultr, and support Ceph object storage built by themselves (users need to configure Cephde S3 object gateway)
- Description: A Ceph S3 object gateway must be configured. The source also mentions Ceph-class object storage from providers such as DigitalOcean, Linode, and Vultr.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 205
- Search keywords: Raysync, Storage, Ceph-class object storage like DigitalOcean/Linode/Vultr, and support Ceph object storage built by themselves (users need to configure Cephde S3 object gateway), SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-206 | S3 API compatible cloud services(For example: Wasabi, Backblaze, MinIO, Meituan Cloud, Didi Cloud and other object storage)

- Knowledge base ID: RS-FEAT-206
- Capability domain: Storage
- Original source text: S3 API compatible cloud services(For example: Wasabi, Backblaze, MinIO, Meituan Cloud, Didi Cloud and other object storage)
- Description: Examples include Wasabi, Backblaze, MinIO, Meituan Cloud, Didi Cloud, and other S3 API-compatible object storage services.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 206
- Search keywords: Raysync, Storage, S3 API compatible cloud services(For example: Wasabi, Backblaze, MinIO, Meituan Cloud, Didi Cloud and other object storage), SMB, Enterprise, Cloud, Multiple Spaces

## Server Deployment

Standalone, primary/standby, load-balanced, multi-port, and high-availability deployments.

### RS-FEAT-208 | Standalone deployment

- Knowledge base ID: RS-FEAT-208
- Capability domain: Server Deployment
- Original source text: Standalone deployment
- Description: This entry describes the Raysync capability “Standalone deployment.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 208
- Search keywords: Raysync, Server Deployment, Standalone deployment, SMB, Enterprise, Multiple Spaces

### RS-FEAT-209 | Dual server and standby deployment

- Knowledge base ID: RS-FEAT-209
- Capability domain: Server Deployment
- Original source text: Dual server and standby deployment
- Description: This entry describes the Raysync capability “Dual server and standby deployment.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 209
- Search keywords: Raysync, Server Deployment, Dual server and standby deployment, Enterprise, Multiple Spaces

### RS-FEAT-210 | Application layer load balancing mode deployment

- Knowledge base ID: RS-FEAT-210
- Capability domain: Server Deployment
- Original source text: Application layer load balancing mode deployment
- Description: This entry describes the Raysync capability “Application layer load balancing mode deployment.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 210
- Search keywords: Raysync, Server Deployment, Application layer load balancing mode deployment, Enterprise, Multiple Spaces

### RS-FEAT-211 | Support 4-layer load balancing mode deployment (LV5, F5 load balancer)

- Knowledge base ID: RS-FEAT-211
- Capability domain: Server Deployment
- Original source text: Support 4-layer load balancing mode deployment (LV5, F5 load balancer)
- Description: This entry describes the Raysync capability “Support 4-layer load balancing mode deployment (LV5, F5 load balancer).” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 211
- Search keywords: Raysync, Server Deployment, Support 4-layer load balancing mode deployment (LV5, F5 load balancer), Enterprise, Multiple Spaces

### RS-FEAT-212 | Multi-port integration

- Knowledge base ID: RS-FEAT-212
- Capability domain: Server Deployment
- Original source text: Multi-port integration
- Description: This entry describes the Raysync capability “Multi-port integration.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.1
- Source location: Raysync Feature list.xlsx / English-New / row 212
- Search keywords: Raysync, Server Deployment, Multi-port integration, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-213 | High availability deployment

- Knowledge base ID: RS-FEAT-213
- Capability domain: Server Deployment
- Original source text: High availability deployment
- Description: This entry describes the Raysync capability “High availability deployment.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 213
- Search keywords: Raysync, Server Deployment, High availability deployment, SMB, Enterprise, Multiple Spaces

## Customized Services

Customization of web branding, clients, portal menus, and access entry points.

### RS-FEAT-215 | Support web customization, including browser icon, website logo, background image, background color, theme color, login box location, etc.

- Knowledge base ID: RS-FEAT-215
- Capability domain: Customized Services
- Original source text: Support web customization, including browser icon, website logo, background image, background color, theme color, login box location, etc.
- Description: This entry describes the Raysync capability “Support web customization, including browser icon, website logo, background image, background color, theme color, login box location, etc..” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 215
- Search keywords: Raysync, Customized Services, Support web customization, including browser icon, website logo, background image, background color, theme color, login box location, etc., Enterprise, Cloud, Multiple Spaces

### RS-FEAT-216 | User client customization

- Knowledge base ID: RS-FEAT-216
- Capability domain: Customized Services
- Original source text: User client customization
- Description: This entry describes the Raysync capability “User client customization.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 216
- Search keywords: Raysync, Customized Services, User client customization, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-217 | Support admin portal to customize the left menu bar of user portal

- Knowledge base ID: RS-FEAT-217
- Capability domain: Customized Services
- Original source text: Support admin portal to customize the left menu bar of user portal
- Description: This entry describes the Raysync capability “Support admin portal to customize the left menu bar of user portal.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.4.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 217
- Search keywords: Raysync, Customized Services, Support admin portal to customize the left menu bar of user portal, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-218 | Disable/enable access to the user portal and external link portal

- Knowledge base ID: RS-FEAT-218
- Capability domain: Customized Services
- Original source text: Disable/enable access to the user portal and external link portal
- Description: This entry describes the Raysync capability “Disable/enable access to the user portal and external link portal.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Cloud, Multiple Spaces
- Explicitly unsupported editions: SMB
- Source version note: 6.7.8.2
- Source location: Raysync Feature list.xlsx / English-New / row 218
- Search keywords: Raysync, Customized Services, Disable/enable access to the user portal and external link portal, Enterprise, Cloud, Multiple Spaces

## Browser High-Speed Transfer Plug-in Supported Systems

Operating systems supported by the browser high-speed transfer plug-in.

### RS-FEAT-220 | Windows7-10

- Knowledge base ID: RS-FEAT-220
- Capability domain: Browser High-Speed Transfer Plug-in Supported Systems
- Original source text: Windows7-10
- Description: This entry describes the Raysync capability “Windows7-10.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 220
- Search keywords: Raysync, Browser High-Speed Transfer Plug-in Supported Systems, Windows7-10, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-221 | Windows Server 2008 and above

- Knowledge base ID: RS-FEAT-221
- Capability domain: Browser High-Speed Transfer Plug-in Supported Systems
- Original source text: Windows Server 2008 and above
- Description: This entry describes the Raysync capability “Windows Server 2008 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 221
- Search keywords: Raysync, Browser High-Speed Transfer Plug-in Supported Systems, Windows Server 2008 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-222 | MacOS 10.11 and above

- Knowledge base ID: RS-FEAT-222
- Capability domain: Browser High-Speed Transfer Plug-in Supported Systems
- Original source text: MacOS 10.11 and above
- Description: This entry describes the Raysync capability “MacOS 10.11 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 222
- Search keywords: Raysync, Browser High-Speed Transfer Plug-in Supported Systems, MacOS 10.11 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-223 | Linux CentOS 7.X and above

- Knowledge base ID: RS-FEAT-223
- Capability domain: Browser High-Speed Transfer Plug-in Supported Systems
- Original source text: Linux CentOS 7.X and above
- Description: This entry describes the Raysync capability “Linux CentOS 7.X and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 223
- Search keywords: Raysync, Browser High-Speed Transfer Plug-in Supported Systems, Linux CentOS 7.X and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-224 | Linux Ubuntu 14.04 and above

- Knowledge base ID: RS-FEAT-224
- Capability domain: Browser High-Speed Transfer Plug-in Supported Systems
- Original source text: Linux Ubuntu 14.04 and above
- Description: This entry describes the Raysync capability “Linux Ubuntu 14.04 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 224
- Search keywords: Raysync, Browser High-Speed Transfer Plug-in Supported Systems, Linux Ubuntu 14.04 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-225 | ARM

- Knowledge base ID: RS-FEAT-225
- Capability domain: Browser High-Speed Transfer Plug-in Supported Systems
- Original source text: ARM
- Description: This entry describes the Raysync capability “ARM.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 225
- Search keywords: Raysync, Browser High-Speed Transfer Plug-in Supported Systems, ARM, SMB, Enterprise, Cloud, Multiple Spaces

## Desktop Client Supported Systems

Operating systems supported by the desktop client.

### RS-FEAT-227 | Windows7 and above

- Knowledge base ID: RS-FEAT-227
- Capability domain: Desktop Client Supported Systems
- Original source text: Windows7 and above
- Description: This entry describes the Raysync capability “Windows7 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 227
- Search keywords: Raysync, Desktop Client Supported Systems, Windows7 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-228 | Windows Server 2008 and above

- Knowledge base ID: RS-FEAT-228
- Capability domain: Desktop Client Supported Systems
- Original source text: Windows Server 2008 and above
- Description: This entry describes the Raysync capability “Windows Server 2008 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 228
- Search keywords: Raysync, Desktop Client Supported Systems, Windows Server 2008 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-229 | MacOS 10.13 and above

- Knowledge base ID: RS-FEAT-229
- Capability domain: Desktop Client Supported Systems
- Original source text: MacOS 10.13 and above
- Description: This entry describes the Raysync capability “MacOS 10.13 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 229
- Search keywords: Raysync, Desktop Client Supported Systems, MacOS 10.13 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-230 | Linux CentOS 7.X and above

- Knowledge base ID: RS-FEAT-230
- Capability domain: Desktop Client Supported Systems
- Original source text: Linux CentOS 7.X and above
- Description: This entry describes the Raysync capability “Linux CentOS 7.X and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 230
- Search keywords: Raysync, Desktop Client Supported Systems, Linux CentOS 7.X and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-231 | Linux Ubuntu 14.04 and above

- Knowledge base ID: RS-FEAT-231
- Capability domain: Desktop Client Supported Systems
- Original source text: Linux Ubuntu 14.04 and above
- Description: This entry describes the Raysync capability “Linux Ubuntu 14.04 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 231
- Search keywords: Raysync, Desktop Client Supported Systems, Linux Ubuntu 14.04 and above, SMB, Enterprise, Cloud, Multiple Spaces

## Command Line Client Supported Systems

Operating systems supported by the command-line client.

### RS-FEAT-233 | Windows7 and above

- Knowledge base ID: RS-FEAT-233
- Capability domain: Command Line Client Supported Systems
- Original source text: Windows7 and above
- Description: This entry describes the Raysync capability “Windows7 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 233
- Search keywords: Raysync, Command Line Client Supported Systems, Windows7 and above, Enterprise, Multiple Spaces

### RS-FEAT-234 | Windows Server 2008R2 and above

- Knowledge base ID: RS-FEAT-234
- Capability domain: Command Line Client Supported Systems
- Original source text: Windows Server 2008R2 and above
- Description: This entry describes the Raysync capability “Windows Server 2008R2 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 234
- Search keywords: Raysync, Command Line Client Supported Systems, Windows Server 2008R2 and above, Enterprise, Multiple Spaces

### RS-FEAT-235 | MacOS 10.12 and above

- Knowledge base ID: RS-FEAT-235
- Capability domain: Command Line Client Supported Systems
- Original source text: MacOS 10.12 and above
- Description: This entry describes the Raysync capability “MacOS 10.12 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 235
- Search keywords: Raysync, Command Line Client Supported Systems, MacOS 10.12 and above, Enterprise, Multiple Spaces

### RS-FEAT-236 | 2.6.26 all above kernel Linux CentOS 6.x

- Knowledge base ID: RS-FEAT-236
- Capability domain: Command Line Client Supported Systems
- Original source text: 2.6.26 all above kernel Linux CentOS 6.x
- Description: This entry describes the Raysync capability “2.6.26 all above kernel Linux CentOS 6.x.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 236
- Search keywords: Raysync, Command Line Client Supported Systems, 2.6.26 all above kernel Linux CentOS 6.x, Enterprise, Multiple Spaces

### RS-FEAT-237 | 2.6.26 all above kernel Linux Ubuntu 14.04-18.04

- Knowledge base ID: RS-FEAT-237
- Capability domain: Command Line Client Supported Systems
- Original source text: 2.6.26 all above kernel Linux Ubuntu 14.04-18.04
- Description: This entry describes the Raysync capability “2.6.26 all above kernel Linux Ubuntu 14.04-18.04.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 237
- Search keywords: Raysync, Command Line Client Supported Systems, 2.6.26 all above kernel Linux Ubuntu 14.04-18.04, Enterprise, Multiple Spaces

## SDK Supported Systems

Operating systems on which the Raysync SDK can run or be integrated.

### RS-FEAT-239 | Windows7 and above

- Knowledge base ID: RS-FEAT-239
- Capability domain: SDK Supported Systems
- Original source text: Windows7 and above
- Description: This entry describes the Raysync capability “Windows7 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 239
- Search keywords: Raysync, SDK Supported Systems, Windows7 and above, Enterprise, Multiple Spaces

### RS-FEAT-240 | Windows Server 2008 and above

- Knowledge base ID: RS-FEAT-240
- Capability domain: SDK Supported Systems
- Original source text: Windows Server 2008 and above
- Description: This entry describes the Raysync capability “Windows Server 2008 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 240
- Search keywords: Raysync, SDK Supported Systems, Windows Server 2008 and above, Enterprise, Multiple Spaces

### RS-FEAT-241 | MacOS 10.11 and above

- Knowledge base ID: RS-FEAT-241
- Capability domain: SDK Supported Systems
- Original source text: MacOS 10.11 and above
- Description: This entry describes the Raysync capability “MacOS 10.11 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 241
- Search keywords: Raysync, SDK Supported Systems, MacOS 10.11 and above, Enterprise, Multiple Spaces

### RS-FEAT-242 | 2.6.26 all above kernel Linux CentOS 6.x

- Knowledge base ID: RS-FEAT-242
- Capability domain: SDK Supported Systems
- Original source text: 2.6.26 all above kernel Linux CentOS 6.x
- Description: This entry describes the Raysync capability “2.6.26 all above kernel Linux CentOS 6.x.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 242
- Search keywords: Raysync, SDK Supported Systems, 2.6.26 all above kernel Linux CentOS 6.x, Enterprise, Multiple Spaces

### RS-FEAT-243 | 2.6.26 all above kernel Linux Ubuntu 14.04-18.04

- Knowledge base ID: RS-FEAT-243
- Capability domain: SDK Supported Systems
- Original source text: 2.6.26 all above kernel Linux Ubuntu 14.04-18.04
- Description: This entry describes the Raysync capability “2.6.26 all above kernel Linux Ubuntu 14.04-18.04.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: Enterprise, Multiple Spaces
- Explicitly unsupported editions: SMB, Cloud
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 243
- Search keywords: Raysync, SDK Supported Systems, 2.6.26 all above kernel Linux Ubuntu 14.04-18.04, Enterprise, Multiple Spaces

## Server Supported Systems

Operating systems, architectures, and TLS capabilities supported by the Raysync server.

### RS-FEAT-245 | Windows7 and above

- Knowledge base ID: RS-FEAT-245
- Capability domain: Server Supported Systems
- Original source text: Windows7 and above
- Description: This entry describes the Raysync capability “Windows7 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 245
- Search keywords: Raysync, Server Supported Systems, Windows7 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-246 | Windows Server 2008 and above

- Knowledge base ID: RS-FEAT-246
- Capability domain: Server Supported Systems
- Original source text: Windows Server 2008 and above
- Description: This entry describes the Raysync capability “Windows Server 2008 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 246
- Search keywords: Raysync, Server Supported Systems, Windows Server 2008 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-247 | All released versions of Linux kernel 2.6.26 and above

- Knowledge base ID: RS-FEAT-247
- Capability domain: Server Supported Systems
- Original source text: All released versions of Linux kernel 2.6.26 and above
- Description: This entry describes the Raysync capability “All released versions of Linux kernel 2.6.26 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 247
- Search keywords: Raysync, Server Supported Systems, All released versions of Linux kernel 2.6.26 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-248 | Linux CentOS 6.X/7.X

- Knowledge base ID: RS-FEAT-248
- Capability domain: Server Supported Systems
- Original source text: Linux CentOS 6.X/7.X
- Description: This entry describes the Raysync capability “Linux CentOS 6.X/7.X.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 248
- Search keywords: Raysync, Server Supported Systems, Linux CentOS 6.X/7.X, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-249 | Linux Ubuntu 12.04 and above

- Knowledge base ID: RS-FEAT-249
- Capability domain: Server Supported Systems
- Original source text: Linux Ubuntu 12.04 and above
- Description: This entry describes the Raysync capability “Linux Ubuntu 12.04 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 249
- Search keywords: Raysync, Server Supported Systems, Linux Ubuntu 12.04 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-250 | Debian 8 and above

- Knowledge base ID: RS-FEAT-250
- Capability domain: Server Supported Systems
- Original source text: Debian 8 and above
- Description: This entry describes the Raysync capability “Debian 8 and above.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 250
- Search keywords: Raysync, Server Supported Systems, Debian 8 and above, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-251 | TLS 1.3

- Knowledge base ID: RS-FEAT-251
- Capability domain: Server Supported Systems
- Original source text: TLS 1.3
- Description: This entry describes the Raysync capability “TLS 1.3.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 251
- Search keywords: Raysync, Server Supported Systems, TLS 1.3, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-252 | IBM AIX 6.5/7.1

- Knowledge base ID: RS-FEAT-252
- Capability domain: Server Supported Systems
- Original source text: IBM AIX 6.5/7.1
- Description: This entry describes the Raysync capability “IBM AIX 6.5/7.1.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 252
- Search keywords: Raysync, Server Supported Systems, IBM AIX 6.5/7.1, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-253 | ARM

- Knowledge base ID: RS-FEAT-253
- Capability domain: Server Supported Systems
- Original source text: ARM
- Description: This entry describes the Raysync capability “ARM.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 253
- Search keywords: Raysync, Server Supported Systems, ARM, SMB, Enterprise, Cloud, Multiple Spaces

## Log Management

System, user, administrator, sharing, and transfer logs, including Syslog integration and log collection.

### RS-FEAT-255 | System management log

- Knowledge base ID: RS-FEAT-255
- Capability domain: Log Management
- Original source text: System management log
- Description: This entry describes the Raysync capability “System management log.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 255
- Search keywords: Raysync, Log Management, System management log, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-256 | Group file transfer log

- Knowledge base ID: RS-FEAT-256
- Capability domain: Log Management
- Original source text: Group file transfer log
- Description: This entry describes the Raysync capability “Group file transfer log.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 256
- Search keywords: Raysync, Log Management, Group file transfer log, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-257 | User login log

- Knowledge base ID: RS-FEAT-257
- Capability domain: Log Management
- Original source text: User login log
- Description: This entry describes the Raysync capability “User login log.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 257
- Search keywords: Raysync, Log Management, User login log, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-258 | File sharing data log

- Knowledge base ID: RS-FEAT-258
- Capability domain: Log Management
- Original source text: File sharing data log
- Description: This entry describes the Raysync capability “File sharing data log.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 258
- Search keywords: Raysync, Log Management, File sharing data log, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-259 | Administrator operation behavior log

- Knowledge base ID: RS-FEAT-259
- Capability domain: Log Management
- Original source text: Administrator operation behavior log
- Description: This entry describes the Raysync capability “Administrator operation behavior log.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 259
- Search keywords: Raysync, Log Management, Administrator operation behavior log, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-260 | Real-time transmission monitoring and transmission log

- Knowledge base ID: RS-FEAT-260
- Capability domain: Log Management
- Original source text: Real-time transmission monitoring and transmission log
- Description: This entry describes the Raysync capability “Real-time transmission monitoring and transmission log.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 260
- Search keywords: Raysync, Log Management, Real-time transmission monitoring and transmission log, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-261 | Transmission logs and operation logs support Syslog integration

- Knowledge base ID: RS-FEAT-261
- Capability domain: Log Management
- Original source text: Transmission logs and operation logs support Syslog integration
- Description: Syslog integration is marked as supported only for SMB and Enterprise; Cloud and Multiple Spaces are marked as not supported.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise
- Explicitly unsupported editions: Cloud, Multiple Spaces
- Source version note: 8.1.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 261
- Search keywords: Raysync, Log Management, Transmission logs and operation logs support Syslog integration, SMB, Enterprise

### RS-FEAT-262 | Collect server logs

- Knowledge base ID: RS-FEAT-262
- Capability domain: Log Management
- Original source text: Collect server logs
- Description: This entry describes the Raysync capability “Collect server logs.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Explicitly supported editions: SMB, Enterprise, Cloud
- Explicitly unsupported editions: Multiple Spaces
- Source version note: 8.1.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 262
- Search keywords: Raysync, Log Management, Collect server logs, SMB, Enterprise, Cloud

## Data Statistics

Statistics for storage, transfer volume, share links, and object storage.

### RS-FEAT-264 | Storage Statistics

- Knowledge base ID: RS-FEAT-264
- Capability domain: Data Statistics
- Original source text: Storage Statistics
- Description: This entry describes the Raysync capability “Storage Statistics.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 264
- Search keywords: Raysync, Data Statistics, Storage Statistics, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-265 | Volume Statistics

- Knowledge base ID: RS-FEAT-265
- Capability domain: Data Statistics
- Original source text: Volume Statistics
- Description: This entry describes the Raysync capability “Volume Statistics.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 265
- Search keywords: Raysync, Data Statistics, Volume Statistics, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-266 | Share Link Statistics

- Knowledge base ID: RS-FEAT-266
- Capability domain: Data Statistics
- Original source text: Share Link Statistics
- Description: This entry describes the Raysync capability “Share Link Statistics.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 266
- Search keywords: Raysync, Data Statistics, Share Link Statistics, SMB, Enterprise, Cloud, Multiple Spaces

### RS-FEAT-267 | Object storage statistics

- Knowledge base ID: RS-FEAT-267
- Capability domain: Data Statistics
- Original source text: Object storage statistics
- Description: This entry describes the Raysync capability “Object storage statistics.” Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 267
- Search keywords: Raysync, Data Statistics, Object storage statistics, SMB, Enterprise, Cloud, Multiple Spaces

## AI Answering Guidelines

1. When answering whether a feature is supported, always name the product edition. If no edition is specified, list the status of all four editions.
2. For blank values, answer “Not specified in source,” not “Not supported.”
3. Quotas, license control, additional payment, Linux-only, upload-only, and similar restrictions must be stated together with the support status.
4. When discussing the version in which a feature became available, cite the `Source version note`. Do not infer availability for entries without a version note.
5. Some similar entries may reflect historical additions or duplicate wording. Semantically related entries may be combined in an answer, but the most specific restrictions and version notes must be retained.

