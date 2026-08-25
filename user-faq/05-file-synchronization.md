### FAQ-SYNC-001 | What is a sync task, and how is it different from a general transfer task?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; navigation differs in version 8.1.8.0 and later
- Feature: File synchronization
- User intent: Understand sync tasks
- Keywords: sync task, general transfer task, repeated transfer

#### Short answer

A sync task keeps a local directory and a server directory aligned according to a direction and schedule. It can upload local content, download server content, or synchronize both ways. A general transfer task sends a selected set of files once; a sync task remains in the task list and can run again at a configured time or interval.

The desktop client shows sync tasks separately from general transfer tasks. A sync task can also apply file-handling choices such as preserving modification time, responding to source updates, filtering files, and choosing what to do when a target file already exists.

#### Version differences

For 8.1.8.0 and later, use the current **Sync** area in the user portal or desktop client. Earlier documentation may describe **Create Sync Directory Task** under **My Files**. The underlying direction and schedule concepts are the same.

#### Important notes

Sync requires the Raysync client and permission to use sync tasks. The administrator can disable sync globally or remove the user's sync permission.

#### Sources

- `client.md` — “General transfer tasks” and “Sync directory task”
- `files.md` — “Create sync task” (source heading: “Creat sync task”)
- `raysync-task.md` — “Create sync Task”
- `v8180-transfer.md` — “Sync”

### FAQ-SYNC-002 | How do I create a sync task?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; current navigation for version 8.1.8.0 and later
- Feature: File synchronization
- User intent: Create a sync task
- Keywords: create sync task, source path, target path, desktop client

#### Short answer

Create the task from **Sync** while the Raysync client is running. Define the paths, direction, frequency, and any optional handling settings before saving it.

#### Prerequisites

- Install and start the Raysync client.
- Log in to the user portal.
- Your account must have sync permission, and the administrator's global sync switch must be enabled.

#### Steps

1. Open **Sync** and select **Create Sync Task**.
2. Enter a task name and select one-way or two-way synchronization.
3. Choose the source path and target path.
4. Select the synchronization frequency.
5. Review optional encryption, file handling, existing-file behavior, and filters.
6. Select **Create**, then use the sync task list to view status and transfer details.

#### Version differences

In documentation for version 8.1.8.0 and later, the primary route is the **Sync** page. Earlier user portal documentation calls the command **Create Sync Directory Task** from **My Files**. The desktop-client workflow also provides a **Sync Task** area.

#### Important notes

The client must be installed and running. Your account needs **Sync Folder** permission, and the administrator's global sync switch must be enabled. Confirm all destructive options before creating the task, especially synchronized target deletion and post-sync source deletion.

#### Sources

- `raysync-task.md` — “Create sync Task” steps
- `cloud.md` — “Sync task”
- `files.md` — “Create sync task” (source heading: “Creat sync task”)
- `v8180-transfer.md` — “Sync”

### FAQ-SYNC-003 | Should I choose one-way or two-way synchronization?

- Product: Raysync
- Audience: End user
- Applies to: One-way sync in all documented versions; two-way sync in version 5.0.3.8 and later
- Feature: File synchronization
- User intent: Choose a sync direction
- Keywords: one-way sync, two-way sync, direction

#### Short answer

Choose one-way sync when one location is authoritative and changes should travel in only one direction. A local source uploads to the server; a server source downloads to the local computer. Choose two-way sync when both the local and server directories may change and you want Raysync to maintain consistency between them.

When two-way sync begins, Raysync first uploads local directory files to the server directory and then downloads server directory files to the local directory. In two-way mode, the source and target roles are not treated as distinct in the same way as one-way mode.

#### Version differences

Two-way synchronization was introduced in v5.0.3.8. Current guides document both one-way and two-way modes; use one-way mode on versions that predate v5.0.3.8.

#### Important notes

Two-way sync can propagate changes in either location. If synchronized deletion is enabled, deleting a file on either side can delete it on the other side. Review deletion and conflict settings before enabling two-way sync on valuable data.

#### Sources

- `files.md` — “Create sync task” (source heading: “Creat sync task”), Direction and Source path
- `cloud.md` — “Sync task,” Direction
- `client.md` — “Sync directory task”
- `release.md` — “v5.0.3.8,” two-way synchronization

### FAQ-SYNC-004 | How do sync upload and sync download directions work?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: File synchronization
- User intent: Set upload or download direction
- Keywords: sync upload, sync download, source directory

#### Short answer

The source path determines a one-way sync direction. If the source is on your computer, Raysync performs a synchronous upload to the server. If the source is on the server, Raysync performs a synchronous download to your computer. Choose the destination on the opposite side as the target path.

For two-way synchronization, the local and server directories exchange changes, so the source and target labels do not have the same one-direction meaning.

#### Version differences

This direction rule is documented consistently in both the user portal and desktop-client guides. For version 8.1.8.0 and later, open the current **Sync** area; earlier versions may expose **Create Sync Directory Task** from **My Files**.

#### Important notes

Verify which side contains the authoritative copy before creating a one-way task. Under **The processing mode of source files after synchronization is complete**, the immediate post-sync option can delete the source directory or its files after an upload or download. The separate **After synchronization, transfer the source file and delete it** option is upload-only: it moves uploaded source files to another path after a delay and can clear them later. Both are destructive and separate from direction.

#### Sources

- `files.md` — “Create sync task” (source heading: “Creat sync task”), Direction and Source path
- `cloud.md` — “Sync task,” Direction and Source path
- `client.md` — “Sync directory task”

### FAQ-SYNC-005 | How often can a sync task run?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; Once from version 6.0.0.8 and Weekly from version 6.3.8.0
- Feature: Sync scheduling
- User intent: Set sync frequency
- Keywords: sync schedule, daily, interval, once, weekly

#### Short answer

A sync task can run once at a specified time, daily at a fixed time, repeatedly at an interval, or weekly on selected days at a specified time. For example, **Every 60 seconds** starts the task each minute, while **Daily 18:22** starts it once per day at 18:22.

The desktop client may show an interval task as **Idle** until its next run, a daily task as **Schedule** before its time, and **Idle (completion time)** after a daily run has completed but before the next scheduled time.

#### Version differences

The **Once** schedule was added in v6.0.0.8, and weekly synchronization was added in v6.3.8.0. Daily fixed-time and interval schedules are documented generally. In 8.1.8.7, plug-in sync handling also gained minute-level file-move frequency and a **Never Delete** option for post-transfer cleanup.

#### Important notes

An administrator can enforce a sync-task frequency. If so, you cannot change the frequency when creating or editing the task in the user portal.

#### Sources

- `files.md` — “Create sync task” (source heading: “Creat sync task”), Sync schedule
- `cloud.md` — “Sync task,” Sync schedule
- `client.md` — “Sync task status description”
- `release.md` — “v6.0.0.8,” synchronize once; “v6.3.8.0,” weekly synchronization
- `release.md` — “v8.1.8.7,” Plugin sync enhancement

### FAQ-SYNC-006 | Can Raysync synchronize local changes in real time?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.3 and later
- Feature: Real-time synchronization
- User intent: Sync immediately after file changes
- Keywords: real-time sync, upload sync, local storage

#### Short answer

Yes, but the documentation limits real-time synchronization to uploads from local storage. When a corresponding local file is modified, Raysync can synchronize the modified file in real time instead of waiting for the next normal schedule.

#### Version differences

Real-time synchronization was introduced in 8.1.8.3. The source documentation does not describe real-time download, two-way real-time sync, or real-time operation with object storage. For those cases, use the supported scheduled modes.

#### Important notes

Real-time mode does not remove the usual prerequisites: the client must be running, the sync feature must be enabled globally, and your account must have sync permission. The documentation limits real-time mode to uploads from local storage; no broader coverage should be assumed.

#### Sources

- `files.md` — “The synchronization feature supports real-time updates”
- `release.md` — “v8.1.8.3,” synchronization feature supports real-time updates
- `v8180-transfer.md` — “Sync”

### FAQ-SYNC-007 | Can a sync task transfer only files that were added or modified?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.8.8.0 and later
- Feature: Incremental sync
- User intent: Avoid duplicate synchronization
- Keywords: source updates, modified files, added files

#### Short answer

Yes. Enable the file-handling option that supports synchronization when the source file is updated. Raysync then synchronizes when source files have been modified or added, which avoids unnecessary duplicate synchronization operations.

This is different from real-time sync. The source-update option decides which content qualifies for another synchronization run; the normal schedule still decides when a task runs unless you use the separately documented real-time upload feature.

#### Version differences

Synchronization triggered by an added or modified source file was added in v6.8.8.0. Real-time upload is a separate feature introduced in 8.1.8.3 and is limited to local storage.

#### Important notes

The source documentation describes modified and added files for this option; it does not say that deletion is included. To propagate deletions, use the separate synchronized-deletion option and understand its data-loss effect first.

#### Sources

- `files.md` — “Synchronous transfer Supports synchronization when the source file is updated”
- `cloud.md` — “Sync task,” source-file update handling
- `release.md` — “v6.8.8.0,” sync when the source file is updated
- `release.md` — “v8.1.8.3”

### FAQ-SYNC-008 | What happens when files are added or deleted after a sync task is created?

- Product: Raysync
- Audience: End user
- Applies to: Source-update behavior in version 6.8.8.0 and later; synchronized deletion in current documented versions
- Feature: Sync file handling
- User intent: Predict added and deleted file behavior
- Keywords: add file, delete file, synchronized deletion

#### Short answer

New or modified source files can be picked up by later runs when source-update synchronization is enabled. Deletion is controlled separately. If **Delete target file synchronously when source deleted** is enabled, deleting a file in one synchronized path also deletes the corresponding file in the other path.

The guide's example is a local directory A synchronized to the server: deleting `test` from local A causes the server copy of `test` to be deleted.

#### Version differences

Source-update synchronization was added in v6.8.8.0. The current guides document synchronized target deletion, but the release list does not identify when that specific option was introduced; do not assume it exists in an older interface unless the option is visible.

#### Important notes

**Destructive behavior:** synchronized deletion can remove the remaining copy on the other side. The option does not support the root directory and cannot be enabled together with **Transfer source files only**. This option is distinct from deleting or moving source content after a completed sync.

#### Sources

- `files.md` — “Delete target file synchronously when source deleted” and source-update handling
- `cloud.md` — “Sync task,” File Handling
- `release.md` — “v6.8.8.0,” sync when the source file is updated

### FAQ-SYNC-009 | How does a sync task handle an existing same-name target?

- Product: Raysync
- Audience: End user
- Applies to: Append from version 5.0.6.8; rename and overwrite-if-newer from version 6.3.8.0; current sync guides include all four choices
- Feature: Sync conflict handling
- User intent: Choose existing-file behavior
- Keywords: overwrite, overwrite if newer, append, rename conflict

#### Short answer

When a sync task finds a same-name target file with different content, its existing-target setting provides these documented choices:

- **Overwrite target file:** replace the existing target content.
- **Overwrite if source newer:** replace the target only when the incoming file's modification time is newer.
- **Append to target file:** add incoming content to the end of the target file; this is not available for object storage.
- **Rename file:** for one-way sync, keep the existing target and rename the incoming source, such as `test(1)`.

#### Version differences

Append-to-target was added in version 5.0.6.8. Rename and **Overwrite if source newer** were added in version 6.3.8.0. Current sync guides document all four choices; the release list does not provide a separate introduction date for unconditional overwrite.

#### Important notes

**Destructive implications:** Overwrite can destroy the previous synchronized target contents, and append modifies that target instead of creating an independent copy; append is unavailable for object storage. One-way rename preserves the existing target by changing the incoming name. Modification-time preservation and **Overwrite if source newer** remain separate sync controls.

#### Sources

- `files.md` — “File update”
- `cloud.md` — “handling of existing target files”
- `release.md` — “v5.0.6.8,” append; “v6.3.8.0,” rename and overwrite-if-newer

### FAQ-SYNC-010 | How does preserving modification time affect synchronized files?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: File timestamps
- User intent: Preserve source timestamps
- Keywords: modification time, timestamp, sync completion

#### Short answer

Enable **Preserve modification time** when the synchronized file should keep the source file's modification time. If you disable it, the target file's modification time becomes the time when the client finishes the transfer.

This setting is useful when another workflow sorts files by modification time or uses timestamps to determine whether a file is newer.

#### Version differences

The behavior is documented consistently across the user portal and client guides.

#### Important notes

Preserving modification time does not itself decide whether an existing file is replaced. Existing-file behavior is controlled separately by overwrite, overwrite-if-newer, append, or rename. If you select **Overwrite if source newer**, verify that the timestamps in the source and target systems reflect the comparison you intend.

#### Sources

- `files.md` — “Preserve modification time Enabled”
- `cloud.md` — “File Handling-Preserve modification time Enabled”
- `client.md` — “Preserve file timestamps after transfer completed”

### FAQ-SYNC-011 | How do sync file filters work?

- Product: Raysync
- Audience: End user
- Applies to: Version 5.0.6.8 and later
- Feature: Sync filters
- User intent: Include or exclude files
- Keywords: file filter, whitelist, blacklist, wildcard, size filter

#### Short answer

Sync filters can allow or exclude files and folders that match configured conditions. Wildcards are supported; for example, a blacklist entry of `test*` filters names that start with `test`. A separate size filter can skip files that exceed the configured size.

#### Version differences

Sync-file filter conditions were added in v5.0.6.8. In earlier space documentation after that release, administrators may define name filters using regular expressions for personal-space sync tasks. In current role-based settings, administrators can provide whitelist/blacklist rules and can prohibit users from setting their own sync filters.

#### Important notes

If filter controls are missing or locked, that can be intentional: an administrator may have prohibited user-defined filtering or assigned a role with fixed rules. Confirm whether a rule is a whitelist or blacklist before running the task, because reversing the choice changes which files transfer.

#### Sources

- `files.md` — “File Filter”
- `cloud.md` — “Filtering-transfer files and folder”
- `v8180-user-roles.md` — “Transfer File Filtering”
- `space.md` — “Space member permissions and transfer configuration”
- `release.md` — “v5.0.6.8,” synchronized-file filter conditions

### FAQ-SYNC-012 | Can I select multiple source directories for one sync task?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.5.8.4 and later
- Feature: Sync source selection
- User intent: Synchronize several folders
- Keywords: multiple source directories, same level, source path

#### Short answer

Yes. When selecting the source folder, Raysync supports choosing multiple paths at the same directory level for transfer. Configure the target and direction as you would for a single-source sync task.

#### Version differences

Selecting multiple same-level source paths was added in version 6.5.8.4. Current desktop-client and user portal guides retain the same-level restriction.

#### Important notes

The sources specifically say multiple paths **of the same level**. They do not document combining arbitrary unrelated levels or provide a workaround when a selection is rejected. Also review **Transfer source files only**: when enabled, the first-layer folder itself is not transferred, while disabling it transfers all files and folders in the directory.

#### Sources

- `files.md` — “Create sync task” (source heading: “Creat sync task”), Source path and “Only transfer source files”
- `cloud.md` — “Sync task,” Source path
- `release.md` — “v6.5.8.4,” multiple same-level source paths

### FAQ-SYNC-013 | Can Raysync move or delete source files after synchronization?

- Product: Raysync
- Audience: End user
- Applies to: Post-sync source deletion from version 6.0.0.8; later cleanup options as noted
- Feature: Post-sync source processing
- User intent: Clear or archive source content
- Keywords: delete source, move source, never delete, destructive

#### Short answer

Yes, through explicit post-sync processing settings. One mode automatically deletes the source directory after synchronization for upload or download. It can either delete the source directories and files, or retain the directory structure and delete only files. A separate upload-only mode can move uploaded source files to another path after a delay and clear them after a configured number of days.

#### Version differences

Basic deletion of source files after sync was added in v6.0.0.8. Retaining the source directory structure while deleting its files was added in v6.6.8.0. Upload sync gained move-then-delete processing in v6.7.8.3. In 8.1.8.7, plug-in sync gained minute-level move frequency and a **Never Delete** option; the detailed guide represents never-delete as `0` days.

#### Important notes

**Destructive behavior:** these settings remove source data after transfer and are not the same as synchronized target deletion. Verify the destination, transfer result, retention interval, and backup policy before enabling them. Use **Never Delete**/`0` when moved files must remain in the archive path.

#### Sources

- `files.md` — “The processing mode of source files after synchronization is complete”
- `cloud.md` — “Sync task,” source-file processing
- `release.md` — “v6.0.0.8,” source deletion; “v6.6.8.0,” retain directory structure; “v6.7.8.3,” move then delete
- `release.md` — “v8.1.8.7,” Plugin sync enhancement

### FAQ-SYNC-014 | How do I pause, resume, disable, or remove a sync task?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Sync task management
- User intent: Stop or control synchronization
- Keywords: pause sync, start sync, disable sync, delete task

#### Short answer

Open the sync task list. A created task can be paused, started again, edited, deleted, or opened to view transfer details. Pausing stops the task from running until you start it again; deleting removes the task definition from the list.

There is no separately documented end-user “global disable” control. If sync is unavailable for every task, the administrator may have disabled the global sync function or removed your **Sync Folder** permission.

#### Version differences

Navigation for version 8.1.8.0 and later uses the **Sync** area. Earlier documentation may place sync creation and management under **My Files**. The global control is documented in both the earlier and current configuration guides.

#### Important notes

Pausing or deleting a task is different from enabling synchronized deletion or post-sync source cleanup. Those file-handling options can delete data when a run completes; stopping the task does not reverse deletions that already occurred.

#### Sources

- `cloud.md` — “Sync task,” task-list actions
- `configuration.md` — “Sync”
- `v8180-transfer.md` — “Sync”
- `client.md` — “Sync Directory Task List”
