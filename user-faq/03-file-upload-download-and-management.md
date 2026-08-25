# File Upload, Download, and Management

### FAQ-FILE-001 | How do I upload a file or folder from the user portal?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Web upload
- User intent: Upload without the client
- Keywords: web upload, upload file, upload folder, progress, web TCP

#### Short answer

In **My Files** or an accessible library under **Group File Folder**, select **Upload file with web** and choose a file, or select **Upload folder with web** and choose a folder. The transfer list in the bottom-right corner of the web page shows upload progress.

**Data-loss warning:** If the applicable existing-target policy overwrites a same-name file, the upload can replace its content. Confirm the destination, filename, and conflict policy before starting.

#### Steps

1. Open the destination directory in the user portal.
2. Choose **Upload file with web** or **Upload folder with web**.
3. Select the local content.
4. Monitor the task in the web transfer list.

#### Version differences

Version 8.1.8.1 added the ability to pause or cancel web transfer tasks without a running client. The basic web upload workflow is otherwise unchanged in the supplied sources.

#### Important notes

Web folder upload does not apply to an empty folder. Upload availability depends on your permission for the destination. A same-name target may also be rejected by an administrator restriction. Do not assume that an existing file will be preserved or replaced until you know the governing policy.

#### Sources

- `files.md` — “File Operations” and “Upload file”
- `group.md` — “Group Folders”
- `release.md` — version 8.1.8.1 web pause/cancel boundary

### FAQ-FILE-002 | How do I upload with the Raysync client?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Client upload
- User intent: Start an accelerated upload
- Keywords: upload with client, desktop client, browser plug-in, transfer list

#### Short answer

From the user portal, select **Upload with client**, choose the file or folder, and monitor progress in the client transfer list. In the standalone desktop client, open **My Files** and select **Upload**, or drag files or folders into the interface.

#### Steps

1. Install and start the desktop client or browser plug-in.
2. Open the desired server directory.
3. Choose **Upload with client** or **Upload**, then select files or folders.
4. Open the client transfer list to view progress and file-level details.

#### Version differences

Version 8.1.8.4 added desktop-client upload and download through Raysync links. Copying a supported link lets the desktop client detect it so you can manually start the transfer; a link can also be entered manually if clipboard detection fails.

#### Important notes

Client upload still follows server permissions, file-format filters, antivirus checks, and conflict settings. A successful local selection does not override those controls.

#### Sources

- `files.md` — “Upload file” and “File Upload and Download through Raysync Links Supported”
- `cloud.md` — “General task”
- `release.md` — version 8.1.8.4 desktop-client Raysync link support

### FAQ-FILE-003 | How do I download a file or folder?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: File download
- User intent: Save server content locally
- Keywords: download, web download, client download, save path

#### Short answer

Select the file or folder. Choose **Download with web** to use the browser, or choose **Download** to use the client. Web-download progress appears in the browser's downloads. Client-download progress appears in the client transfer list, and the completed content is saved to the selected path.

#### Steps

1. Select the server file or folder.
2. Choose the web or client download action.
3. If prompted by the client, select a local path.
4. Monitor the appropriate transfer list.
5. For a client download, use **Open File Directory** to locate the result.

#### Version differences

Version 8.1.8.4 added desktop-client handling of Raysync links. Version 8.1.8.7 notes that a single-file HTTP download no longer forces compression.

#### Important notes

Download requires permission. A share-download link permits downloading only when its creator and server settings allow it. An invite-upload link serves a different purpose and must not be treated as a download link.

#### Sources

- `files.md` — “Download file” and “File Upload and Download through Raysync Links Supported”
- `share-link.md` — “Access the share link”
- `invitation-link.md` — “Visit the invite to upload link”
- `release.md` — version 8.1.8.4 link transfer and version 8.1.8.7 HTTP download changes

### FAQ-FILE-004 | How do I create a folder in Raysync?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Folder creation
- User intent: Organize files in a new directory
- Keywords: New Folder, create folder, My Files, Group File Folder

#### Short answer

Open the destination directory, select **New Folder**, enter a folder name, and select **Create**. The initial default name shown by the portal is **New Folder**, which you can replace before creation.

#### Steps

1. Open **My Files** or a group file library where you have permission.
2. Select **New Folder**.
3. Enter the desired name.
4. Select **Create**.

#### Version differences

The supplied sources do not document a version-specific change to this operation.

#### Important notes

Folder creation works in the no-client web mode. In a group file library or invite-upload link, the available action depends on permissions and link configuration. Web folder upload cannot upload an empty local folder, but creating an empty folder directly with **New Folder** is a separate operation.

#### Sources

- `files.md` — “Create a new folder” and “File Operations”
- `group.md` — “Group Folders”
- `invitation-link.md` — “Visit the invite to upload link”

### FAQ-FILE-005 | How do I copy, move, rename, or delete files?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: File management
- User intent: Manage content in the portal
- Keywords: copy, move, rename, delete, file operation

#### Short answer

Select the file or folder, then choose the required action from the toolbar or operation menu. **Move** asks for a destination and uses **Move here**; **Copy** asks for a destination and uses **Copy to this**; **Rename** makes the name editable; **Delete** removes the selected item according to the server's deletion policy.

#### Version differences

The supplied sources do not document a version-specific change to the user selection sequence. Whether **Delete** removes an item directly or sends it to the recycle bin depends on administrator policy.

#### Important notes

**Data-loss warning:** A direct delete or an emptied recycle bin permanently removes the selected content in the documented workflow. Confirm the selected file or folder before choosing **Delete**.

These actions have different consequences:

- **Copy** keeps the source and creates another item.
- **Move** changes the item's location.
- **Rename** changes its name; a virtual directory cannot be renamed from the client side.
- **Delete** may move the item to the recycle bin or delete it directly, depending on administrator policy.
- **Overwrite** is not a normal delete: it replaces existing target-file content during a transfer.

#### Sources

- `files.md` — “Rename,” “Delete files,” “Moving files,” and “Copy files”
- `v8180-security.md` — “Delete files” and “Manual file deletion”

### FAQ-FILE-006 | Can I drag and drop files to upload them?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Drag-and-drop upload
- User intent: Upload by dragging local content
- Keywords: drag and drop, upload, file manager, My Files

#### Short answer

Yes. In your operating system's file manager, select a file or folder, hold the left mouse button, drag it over the Raysync file list, and release it when the page shows the destination such as **Upload to My Files** or the current directory.

#### Steps

1. Open the destination directory in the Raysync user portal.
2. Select the local files or folders in your file manager.
3. Drag them over the portal's file-list area.
4. Wait for the destination indicator, then release the mouse button.
5. Monitor upload progress in the applicable transfer list.

#### Version differences

No version-specific drag-and-drop change is documented in the supplied sources.

#### Important notes

Drag-and-drop upload does not bypass upload permissions, file-format limits, existing-file restrictions, antivirus scanning, or isolation. Review the destination indicator before releasing to avoid uploading to the wrong directory.

#### Sources

- `files.md` — “Upload file” and “Drag and drop upload”
- `cloud.md` — “General task”

### FAQ-FILE-007 | Which files can I preview online?

- Product: Raysync
- Audience: End user
- Applies to: Current documented user portal
- Feature: Online preview
- User intent: View a file without downloading it
- Keywords: preview, image, Office, video, audio, PDF

#### Short answer

Select the file name to open online preview. The guide lists images (`png`, `jpg`, `gif`, `jpeg`, `bmp`, `ico`, `svg`), Office-type content (`pdf`, `doc`, `docx`, `ppt`, `pptx`, `xls`, `xlsx`, `csv`), video (`mp4`, `avi`, `mov`, `mxf`, `mpg`), and audio (`aac`, `aiff`, `aif`, `m4a`, `mp3`, `WAV`).

#### Version differences

Version 8.1.8.0 added the audio formats `.m4a`, `.aif`, `.aiff`, and `.aac`. Version 8.1.8.3 added preview-only behavior for shared files when used with the client.

#### Important notes

Except for PDF, Office-file preview requires a separate service installation by the administrator. Some video and audio files require the client. For a share-download link with **Allow Downloaded** disabled, web recipients can only view the list and cannot preview or download, while client recipients can preview but cannot download.

#### Sources

- `files.md` — “File preview” and “Support share file preview only”
- `share-link.md` — “Create share link”
- `release.md` — version 8.1.8.0 audio formats and version 8.1.8.3 preview-only sharing

### FAQ-FILE-008 | What are personal files in Raysync?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Personal files
- User intent: Understand the My Files area
- Keywords: My Files, personal files, personal directory, storage

#### Short answer

Personal files are the files and folders in your individual Raysync file directory, shown to you in **My Files**. You can perform the file actions made available to your account, such as upload, download, create a folder, rename, copy, move, delete, search, inspect folder properties, decompress supported archives, preview files, or create a sync task when permitted.

#### Version differences

The supplied sources do not document a version-specific change to the end user's **My Files** area.

#### Important notes

Your visible operations depend on account permissions and server configuration. Deleting a personal file may send it to a personal recycle bin or remove it directly, according to administrator policy.

#### Sources

- `files.md` — “My Files” and “File Operations”
- `v8180-recycle-bin.md` — “Personal file” recycle bin

### FAQ-FILE-009 | What are group files and what can I do with them?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Group files
- User intent: Collaborate in a group file library
- Keywords: Group File Folder, group file library, shared directory, permission

#### Short answer

A group file library is a shared directory for multi-user collaboration. In the user portal, select **Group File Folder** in the left navigation, open a group library, and work with its files and folders.

Where the available actions allow it, you can upload, download, create sync tasks, create folders, delete items, and create share-download links. These actions follow the same basic workflows as personal files.

#### Version differences

The supplied sources do not document a version-specific change to the end-user **Group File Folder** workflow.

#### Important notes

Only actions allowed for your group membership are available. An operation that is not shown or is denied is outside the file-operation access assigned to you for that group library.

#### Sources

- `group.md` — “Group Folders”
- `v8180-group-management.md` — “Group file library” and “Group permission”
- `v8180-file.md` — “Group file”

### FAQ-FILE-010 | Why can I not see hidden files in the file list?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.8.8.0 and later when an administrator enables the restriction
- Feature: File visibility
- User intent: Understand missing hidden files
- Keywords: hidden files, file list, visibility, permissions

#### Short answer

An administrator can enable **Do not show hidden files** for your account or user role. When enabled, the Raysync file list does not display files whose names start with `.`. The user-role documentation for version 8.1.8.0 and later also says those hidden files cannot be transferred.

#### Version differences

Version 6.8.8.0 adds the ability to hide files from the file list. The user-role documentation for version 8.1.8.0 and later additionally states that files hidden by this setting cannot be transferred.

#### Important notes

This is an administrator-controlled restriction; the sources do not document an end-user override. A hidden item is not deleted, recycled, isolated, or overwritten. In version 8.1.8.0 and later, however, the current user-role guide explicitly says a hidden file covered by the setting cannot be transferred.

#### Sources

- `v8180-user-roles.md` — “User Roles” permission setting, “Do not show hidden files”
- `local-user.md` — “Local User,” “Do not show hidden files”
- `release.md` — version 6.8.8.0 hidden-file display setting

### FAQ-FILE-011 | Can a deleted file be recovered from the recycle bin?

- Product: Raysync
- Audience: End user
- Applies to: Versions and storage policies with recycle-bin retention
- Feature: Recycle-bin recovery
- User intent: Recover a deleted personal or group file
- Keywords: recycle bin, recover, deleted file, personal file, group file

#### Short answer

Yes, if the deletion policy moved the item to the recycle bin and it has not been emptied. The documented recycle-bin pages allow an administrator to select a personal user's recycle bin or a group file library's recycle bin and recover selected files. Ask your administrator to recover the item.

#### Version differences

The supplied sources identify recycle bins for personal files and group file libraries but do not document a version-specific end-user recovery control. Recovery is an administrator prerequisite in the available workflow.

#### Important notes

Recovery is not available for a file that was deleted directly, has already been removed by emptying the recycle bin, or was overwritten rather than recycled. Isolation is also separate: an isolated file was moved by a security control, not by normal deletion.

#### Sources

- `file.md` — “Files” recycle-bin overview
- `v8180-recycle-bin.md` — “Personal file” and “Group file library”
- `v8180-security.md` — “Manual file deletion”

### FAQ-FILE-012 | What happens when the recycle bin is emptied?

- Product: Raysync
- Audience: End user
- Applies to: Versions and storage policies with recycle-bin retention
- Feature: Permanent removal
- User intent: Understand emptying the recycle bin
- Keywords: empty recycle bin, permanent delete, recover, data loss

#### Short answer

Emptying a personal or group recycle bin removes the selected retained files rather than recovering them. The documented empty/recover controls are on administrator pages, so an ordinary end user should ask the administrator about recovery before the recycle bin is emptied.

#### Version differences

The supplied sources do not document an end-user command for emptying the recycle bin. The available workflow places the empty/recover choice with an administrator.

#### Important notes

**Data-loss warning:** Emptying the recycle bin is the permanent-removal path in the documented workflow. It is not equivalent to a normal delete that first retains an item in the recycle bin. It is also unrelated to overwriting file content or moving a security-detected file into isolation. Confirm the exact personal user or group library and selected files before requesting this action.

#### Sources

- `v8180-recycle-bin.md` — “Personal file” and “Group file library”
- `file.md` — recycle-bin overview
- `v8180-security.md` — “Delete files”

### FAQ-FILE-013 | Why is my uploaded file missing from its user portal folder and shown in the isolation zone?

- Product: Raysync
- Audience: End user
- Applies to: Uploads placed in the isolation zone
- Feature: Isolation zone
- User intent: Understand a quarantined upload
- Keywords: isolation zone, missing upload, original folder, quarantine

#### Short answer

When Raysync isolates an upload, it moves the file out of its intended user portal folder and into the isolation zone. That move is why the file is absent from the original folder after upload.

The isolation view lists isolated items and can show information such as the file name, isolation time, and detected virus type where applicable.

#### Version differences

The supplied current and legacy security guides describe the same user-visible outcome: a detected file is moved to the isolation zone. No different end-user restore workflow is documented.

#### Important notes

Isolation is not normal deletion, recycle-bin retention, overwrite, or permanent removal. The supplied sources do not document an end-user release or restore action, so the item remains outside its intended folder unless an administrator handles it.

#### Sources

- `files.md` — “Isolation zone”
- `security.md` — “Antivirus” and “Detective Sensitive words”
- `v8180-security.md` — “Antivirus” and “Sensitive words”
- `v8180-isolation-zone.md` — “Isolation zone”

### FAQ-FILE-014 | Why can I upload only new files?

- Product: Raysync
- Audience: End user
- Applies to: Transfers where Only upload new files is enabled
- Feature: Upload restriction
- User intent: Understand rejection of an existing filename
- Keywords: upload new only, same name, rejected upload, existing target

#### Short answer

With **Only upload new files**, an upload succeeds when the destination does not already contain a file with that name. A same-name upload is rejected instead of replacing the existing file.

#### Version differences

The supplied sources do not establish when **Only upload new files** was introduced or document a version-specific difference in what the end user experiences.

#### Important notes

The existing target remains unchanged when the incoming same-name upload fails.

#### Sources

- `v8180-user-roles.md` — “User Roles” permission setting, “File upload limit”
- `local-user.md` — “Local User,” “Upload file option”
- `space.md` — “Space member permissions and transfer configuration,” “Upload file options”
- `files.md` — sync-task “File update” conflict choices

### FAQ-FILE-015 | Why does Raysync say I do not have permission for a file operation?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: File permissions
- User intent: Understand an unavailable or denied action
- Keywords: permission denied, group permission, upload, download, delete

#### Short answer

Raysync limits file operations through account permissions and, in a group file library, the permissions attached to group membership. The available upload, download, folder, sync, share, and delete actions can therefore differ between users and locations. An unavailable or denied action means the applicable permission set does not include that operation.

#### Version differences

The supplied sources do not document a version-specific difference in the end-user response to a permission denial.

#### Important notes

The permission model applies to both displayed actions and attempted operations. The supplied sources do not document an end-user method to override assigned access.

#### Sources

- `group.md` — “Group Folders”
- `v8180-group-management.md` — “Group file library” and “Group permission”
- `files.md` — “Create sync task” permission prerequisite

### FAQ-FILE-016 | Which file operations work without a running client?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; web task pause/cancel from version 8.1.8.1
- Feature: No-client web operations
- User intent: Manage files using only the browser
- Keywords: without client, web mode, upload, download, copy, move, delete

#### Short answer

Using only the browser, the user portal supports creating a folder, invite upload, normal upload, normal download, share download, copy, move, delete, folder properties, and rename. These are the documented browser-only capabilities; the automatic fallback trigger is covered in the client-availability FAQ.

#### Version differences

Starting in version 8.1.8.1, users can pause or cancel web transfer tasks without the client. This change affects web task control only; it does not make every client feature available in the browser.

#### Important notes

Creating a sync-task directory and some video preview operations require a client. Web folder upload does not apply to an empty folder. All browser-only operations still require the applicable file permission. A share-download link and invite-upload link remain distinct: the former delivers content for download, while the latter receives uploaded content.

#### Sources

- `files.md` — “Start the client,” “File Operations,” “Upload file,” and “File preview”
- `share-link.md` — “Access the share link”
- `invitation-link.md` — “Visit the invite to upload link”
- `release.md` — version 8.1.8.1 web pause/cancel boundary
