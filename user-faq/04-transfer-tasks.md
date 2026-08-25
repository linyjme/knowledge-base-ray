# Transfer Tasks

### FAQ-TRANSFER-001 | What is a general transfer task?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: General transfer task
- User intent: Understand one-time transfers
- Keywords: general transfer task, upload, download, one-time transfer

#### Short answer

A general transfer task is a one-time upload or download. It uploads local files or folders from the client to server storage, or downloads files or folders from server storage to the client. It is different from a sync task, which synchronizes directories on a schedule or in both directions, and from peer-to-peer transfer, which sends data between client devices.

General transfer tasks can be created from the desktop client or through the user portal with the client or web transfer mode, depending on server configuration.

#### Version differences

The definition is consistent across the supplied user guides. Version 8.1.8.1 added web pause and cancel controls, but did not change what a general transfer task is.

#### Important notes

A general transfer task is not automatically recurring. For repeated directory synchronization, use a sync task when your account and server permit it. The client transfer list groups general tasks separately from sync tasks and peer-to-peer tasks.

#### Sources

- `client.md` — “General transfer tasks”
- `cloud.md` — “Create transfer task” and “General task”
- `create-task.md` — “Start transfer”
- `release.md` — version 8.1.8.1 web pause/cancel boundary

### FAQ-TRANSFER-002 | What is the difference between a web transfer and a client transfer?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Transfer modes
- User intent: Choose web or accelerated client transfer
- Keywords: web transfer, client transfer, desktop client, browser plug-in, web TCP

#### Short answer

A web transfer sends data through the user portal's web TCP mode without a running client. A client transfer sends data through an installed Raysync client component for high-speed transfer. The selected mode determines which capabilities are available and where progress is shown.

The server can allow only web transfer, only client transfer, or the default combination of both. This FAQ compares transfer modes; the desktop client versus browser plug-in FAQ explains which installed component to choose.

#### Version differences

Version 8.1.8.1 added pause and cancel controls for web tasks without the client.

#### Important notes

Web mode supports a limited browser-only feature set. Client mode is required for client-dependent features. If the expected mode is absent, ask the administrator which transfer type the server allows.

#### Sources

- `files.md` — “Start the client” and “File Operations”
- `create-task.md` — “Download the client” and “Start transfer”
- `configuration.md` — “Transfer settings”
- `v8180-transfer.md` — “Transfer”
- `release.md` — version 8.1.8.1

### FAQ-TRANSFER-003 | How do I start an upload or download transfer?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Start transfer
- User intent: Create a general transfer task
- Keywords: start upload, start download, My Files, transfer task

#### Short answer

Start a general transfer task by choosing an upload action for local content going to server storage, or a download action for selected server content going to your computer. You can start it from **My Files** or a library under **Group File Folder**, using the web or client action available to you. The file upload and download FAQs provide the detailed button-by-button procedures.

#### Version differences

Version 8.1.8.4 added desktop-client transfer through Raysync links. Version 8.1.8.7 changed single-file HTTP download so it no longer forces compression.

#### Important notes

You need file-operation permission for the source and destination. This overview does not replace the procedure-specific restrictions: web folder upload does not apply to empty folders, and client transfers require the installed component to be running.

#### Sources

- `files.md` — “Upload file” and “Download file”
- `cloud.md` — “General task”
- `release.md` — version 8.1.8.4 and version 8.1.8.7

### FAQ-TRANSFER-004 | Where can I see transfer progress and task details?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Task monitoring
- User intent: Check progress, speed, and status
- Keywords: progress, speed, transfer list, task details, error reason

#### Short answer

For client transfers, open **Transfer List** from the user portal's upper-right controls, the client icon, or the client's right-click menu. For web uploads, use the transfer list in the bottom-right corner of the portal. Web downloads also appear in the browser's downloads.

Open the relevant task details to see file-level progress, status, and error reasons.

#### Version differences

Version 8.1.8.6 added client task sorting and creation-time filtering. Version 8.1.8.7 added filtering by task name and task status.

#### Important notes

Use the progress location associated with the mode that started the transfer. Client task-list management actions are covered in the client transfer-list FAQ.

#### Sources

- `client.md` — “Transfer List”
- `files.md` — “Upload file” and “Download file”
- `v8180-transfer-task.md` — “Client tasks and Web tasks”
- `release.md` — version 8.1.8.6 and version 8.1.8.7

### FAQ-TRANSFER-005 | How do I pause, resume, or cancel a transfer task?

- Product: Raysync
- Audience: End user
- Applies to: Client tasks in all documented versions; web pause/cancel from version 8.1.8.1
- Feature: Task control
- User intent: Temporarily stop, restart, or cancel a transfer
- Keywords: pause, resume, start, cancel, delete task, batch operation

#### Short answer

In the client transfer list, use **Pause** to stop work temporarily and **Start** to resume a paused task. The client source also documents **Delete** for a task, but it does not specify whether deleting an active task is the client cancellation action, whether it only removes the task record, or whether it does both.

For web transfers, version 8.1.8.1 and later allows pause or cancel without the client.

#### Version differences

Web pause and cancel begin at version 8.1.8.1. Client pause/start controls are documented for the general transfer list without a later version boundary.

#### Important notes

Do not treat **Delete** and **Cancel** as proven equivalents in the client. The sources also do not state that deleting a task record deletes transferred source or destination files. If you must permanently cancel an active client task rather than pause it, confirm the intended **Delete** behavior with your administrator or support. A sync task disabled by an administrator cannot be started by the user.

#### Sources

- `client.md` — “Transfer List”
- `cloud.md` — “General task”
- `v8180-transfer-task.md` — “Client tasks and Web tasks”
- `release.md` — version 8.1.8.1 web pause/cancel

### FAQ-TRANSFER-006 | Does Raysync resume an interrupted transfer from where it stopped?

- Product: Raysync
- Audience: End user
- Applies to: Web upload support documented from version 5.0.8.8; other modes as documented by task controls
- Feature: Breakpoint resume
- User intent: Continue after interruption
- Keywords: breakpoint resume, interrupted upload, retry, resume transfer

#### Short answer

Raysync's release history documents web file upload resuming from where it stopped beginning in version 5.0.8.8, without requiring the client. The current client task list also provides **Start** and **Retry** actions for stopped or failed tasks.

#### Steps

1. Open the transfer list used by the interrupted task.
2. Select the task.
3. Use **Start** to resume a paused task or **Retry** for an available failed task.
4. Check file-level details for its current status or error reason.

#### Version differences

The explicit resume-from-breakpoint statement in the supplied sources concerns web upload from version 5.0.8.8. The sources do not claim identical behavior for every transfer type, protocol, or conflict condition.

#### Important notes

A source file that changes before transfer may be held by the configured stability check rather than resumed immediately. Do not assume that retry overrides permissions, file filters, or an administrator-disabled sync task.

#### Sources

- `release.md` — version 5.0.8.8 web upload breakpoint resume
- `client.md` — “Transfer List” and “Advanced Settings”

### FAQ-TRANSFER-007 | How does transfer priority affect my tasks?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.6 and later when transfer priority is enabled
- Feature: Transfer priority
- User intent: Understand bandwidth scheduling
- Keywords: transfer priority, user role, bandwidth, task speed

#### Short answer

When transfer priority is enabled, the priority assigned to your user role can affect how available bandwidth is scheduled and therefore the speed your tasks receive. It is not controlled by moving a task higher or lower in your desktop client list.

#### Version differences

User transfer priority is listed as a new capability in version 8.1.8.6. Earlier documented versions do not describe this role-based priority system.

#### Important notes

Transfer priority is assigned through a user role, not set per task by an end user. The source mentions bandwidth sharing with an "inviter/sharer," but it does not define the participants for a particular transfer, the direction of sharing, or the allocation calculation; do not infer a specific relationship. If a task receives less bandwidth than expected, ask your administrator whether assigned transfer priority applies.

#### Sources

- `v8180-transfer.md` — “Transfer” and “Transfer priority”
- `release.md` — version 8.1.8.6

### FAQ-TRANSFER-008 | How many transfers or files can run at the same time?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; multi-channel transfer documented in version 8.1.8.6
- Feature: Transfer concurrency
- User intent: Configure parallel work
- Keywords: task parallel, parallel files, concurrency, multi-channel

#### Short answer

In client transfer settings, you can set the maximum parallel upload tasks and maximum parallel download tasks, each up to 10. You can also set the number of parallel files per task. The default file-parallel value is **Automatic**, calculated from the number of CPU cores.

#### Version differences

Version 8.1.8.6 added multi-channel transfer. This is transport-level channel concurrency for sending data over multiple channels on high-bandwidth networks; it does not change the configured task-parallel or files-per-task limits.

#### Important notes

Multi-channel transfer requires server-side ports. The client guide lists TCP/UDP ports `2542`, `2642`, and `2472`; for encrypted multi-channel transfer it lists `2453`, `2643`, and `2743`. Opening ports is an administrator prerequisite. Parallel settings do not override server speed limits, role priority, or available network capacity.

#### Sources

- `client.md` — “Transfer” settings
- `cloud.md` — “Client setting” and “Task and file parallel”
- `release.md` — version 8.1.8.6 multi-channel transfer

### FAQ-TRANSFER-009 | How do upload and download speed limits work?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Bandwidth limits
- User intent: Control or understand transfer speed
- Keywords: speed limit, bandwidth, upload limit, download limit, minimum speed

#### Short answer

The client can set a maximum upload speed and maximum download speed for a single task. If no maximum is set, the task uses the maximum available local bandwidth by default. The client also provides minimum send and receive speed settings intended for unstable networks where bandwidth is underused.

The server can impose a global maximum upload/download speed and time-period limits. Group-library speed limits and role-based transfer priority can further affect observed speed.

#### Version differences

The client and server limit concepts apply across the supplied guides. Version 8.1.8.6 added role-based transfer priority, which can influence allocation in addition to numeric limits.

#### Important notes

The guide suggests setting minimum send/receive speed to about half of the current transmitting client's bandwidth, or to the server bandwidth if that is lower. This is a documented guideline, not a guarantee. Client settings cannot exceed an administrator-imposed cap.

#### Sources

- `client.md` — “Bandwidth”
- `cloud.md` — “Client setting” and “Bandwidth”
- `configuration.md` — “Transfer settings”
- `v8180-transfer.md` — “Transfer”
- `release.md` — version 8.1.8.6 transfer-priority boundary

### FAQ-TRANSFER-010 | Can Raysync skip a file that already exists?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions where the relevant option is available
- Feature: Existing-file handling
- User intent: Avoid downloading or retransmitting unchanged data
- Keywords: skip existing, only download new files, unchanged file, Rsync

#### Short answer

No universal **skip every existing filename** option is documented for all uploads and downloads.

- **Only download new files** applies to downloads; the guide says a download fails when the target already exists and has not been modified.
- **Rsync verification** compares data, skips matching portions, and transfers different portions.
- **Overwrite**, **overwrite if source newer**, **append**, and **rename** are conflict policies, not skip-all settings.

#### Version differences

The release history documents Rsync download verification in version 5.0.2.8, and later client guides retain the option. The supplied sources do not identify a later change to **Only download new files**.

#### Important notes

Choose the policy that matches the task and direction. Do not assume that **Only download new files** applies to uploads or that Rsync protects an existing target from a separately configured overwrite policy.

#### Sources

- `client.md` — “Advanced Settings,” “Enable Rsync check,” and “Only download new files”
- `cloud.md` — “Client setting,” “Incremental Transfer,” and “Download files”
- `release.md` — version 5.0.2.8 Rsync download verification

### FAQ-TRANSFER-011 | What happens when a target file has the same name?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions where conflict options are available
- Feature: File conflicts
- User intent: Choose overwrite, append, or rename behavior
- Keywords: overwrite, overwrite if newer, append, rename, same name

#### Short answer

Raysync documents four existing-target choices:

- **Overwrite target file** replaces the existing content directly.
- **Overwrite if source newer** replaces it only when the incoming file's modification time is newer.
- **Append to target file** adds incoming content to the end and is not applicable to object storage.
- **Rename file** preserves the existing target and renames the incoming source, for example from `test` to `test(1)`.

#### Version differences

The same general conflict choices appear across the supplied current and legacy transfer guides; no different end-user meaning is documented for these options.

#### Important notes

**Data-loss warning:** Overwrite replaces existing target content. It is not recycling and does not provide the recycle-bin recovery described for a normal file deletion. Confirm the desired policy before starting a transfer or sync task.

#### Sources

- `cloud.md` — “Handling of existing target files”
- `files.md` — sync-task “File update”

### FAQ-TRANSFER-012 | What does hash verification do?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Hash verification
- User intent: Verify file integrity
- Keywords: hash verification, integrity, retransmit, client setting

#### Short answer

When hash verification is enabled, Raysync compares the local and server file hashes during upload or download. If the hashes differ, the file is retransmitted. If they match, no hash-triggered retransmission is needed and Raysync continues the task's normal processing. This helps ensure file integrity and correctness.

#### Version differences

The capability applies across the supplied client guides. Before and after version 8.1.8.0, the administrator can force hash verification on for clients. In version 8.1.8.0 and later, the administrator can also limit hash-verification speed to control server disk read/write usage.

#### Important notes

An administrator-enforced hash setting takes precedence over an end-user preference. Hash verification is different from Rsync verification: hash verification validates whole-file equality, while Rsync can skip matching portions and transfer different portions.

#### Sources

- `client.md` — “Advanced Settings” and “Enable hash check”
- `cloud.md` — “Transfer Security”
- `configuration.md` — “Client settings”
- `v8180-transfer.md` — “Client app” and “Limit hash verification speed”

### FAQ-TRANSFER-013 | How do I use encrypted transfer?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Transfer encryption
- User intent: Protect data in transit
- Keywords: encrypted transfer, transfer security, client settings, sync task

#### Short answer

In the desktop client, open **Settings > Advanced Settings** and enable **Priority to use encrypted transfer**. In the cloud-style client settings, open **Transfer Security** and enable **Enable encrypted for transfer**. For a sync task, enable encrypted transfer in that task's **Security** settings before starting it.

#### Version differences

The supplied sources do not document a version-specific change to these end-user encryption controls.

#### Important notes

If an administrator forces encrypted transfer, it remains enabled regardless of a local preference. Encrypted multi-channel transfer also requires server ports `2453`, `2643`, and `2743`; this is an administrator prerequisite.

#### Sources

- `client.md` — “Advanced Settings”
- `cloud.md` — “Transfer Security”
- `configuration.md` — “Client settings”
- `v8180-transfer-task.md` — “Security”

### FAQ-TRANSFER-014 | What do Rsync verification and data compression do?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions where options are available
- Feature: Incremental transfer and compression
- User intent: Reduce retransmitted data or improve efficiency
- Keywords: Rsync, incremental transfer, compression, matching portions

#### Short answer

**Rsync verification** compares the local and server versions. The guides say that matching portions are skipped and different portions are transferred when only part of a file differs. They also say that a file is retransmitted when the overall Rsync check differs. The sources do not define the exact condition that selects changed-data transfer instead of whole-file retransmission.

**Data compression** compresses data before transmission to improve transfer efficiency. It is a separate setting and does not perform integrity verification.

#### Version differences

The release history documents librsync file-change checking and later Rsync download verification before the version 8.1.8.x series. Version 8.1.8.7 changes HTTP behavior so a single-file HTTP download no longer forces compression.

#### Important notes

Rsync does not mean that a same-name target is automatically safe from overwrite; existing-file handling remains a separate policy. Compression may not always apply to HTTP single-file downloads in current versions.

#### Sources

- `client.md` — “Transfer” and “Advanced Settings”
- `cloud.md` — “Incremental Transfer” and “Advanced”
- `release.md` — version 5.0.2.8, version 5.0.0.8, and version 8.1.8.7

### FAQ-TRANSFER-015 | Where can I see transfer logs and failure details?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Transfer logs and details
- User intent: Review a task or provide diagnostics
- Keywords: transfer log, task details, failure reason, client log

#### Short answer

For a failed client task, open **Transfer List**, select or double-click the task, and inspect the file-level status and error reason. Then right-click the client and select **Error Detection** to check the client and program versions, port connectivity, startup privilege, UDP speed, and client/server configuration information.

The guide says **Error Detection** can generate a diagnostic report and automatically fix detected problems. If support needs additional evidence, collect the current day's client logs using the separate client log-collection workflow.

#### Version differences

The supplied sources do not document a version-specific change to this end-user failure-diagnosis workflow.

#### Important notes

If **Error Detection** reports a failed service-port connection, contact the administrator to verify the server ports. If UDP transfer is unexpectedly slow, use the documented UDP speed test. Collect logs before their configured retention period expires.

#### Sources

- `client.md` — “Transfer List,” “Error detection,” and “Log Setting”

### FAQ-TRANSFER-016 | What should I know about a server task issued by an administrator?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Administrator-issued server task
- User intent: Prepare the client to receive a centrally issued task
- Keywords: server task, default server, online client, upload task, download task

#### Short answer

An administrator-issued server task transfers between server storage and one or more client devices. From the end-user perspective, your responsibility is to install and start the Raysync client, configure and log in to the correct default server, and keep the client online. The administrator creates and monitors the task.

If the source path is on the client, the task uploads from the client to the server. If the source is on the server, it downloads to the client. Tasks can run once or according to an administrator-defined interval, daily time, or weekly schedule.

#### Version differences

The supplied sources do not document a version-specific change to the end user's preparation for an administrator-issued server task.

#### Important notes

The client device must show as online for the issued task to run normally. The administrator may specify selected online clients or all online clients. Server-task source and target paths may use system variables.

**Data-loss warning:** Administrator-issued task options can propagate a deletion from one side to the other, automatically delete the source directory after synchronization completes, or overwrite an existing target file. Before the task runs, verify the resolved local path, server path, direction, schedule, deletion options, and existing-target policy with the administrator. If any of those details are unexpected, contact the administrator before leaving the client online for the task.

#### Sources

- `server-task.md` — “The client configures the default server,” “Create server task,” and “Task monitoring”
- `tasks.md` — “Server Task”
- `v8180-transfer-task.md` — “Server task”
- `client.md` — “Default server”
