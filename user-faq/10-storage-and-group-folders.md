### FAQ-STORAGE-001 | What is the difference between personal files and group files in Raysync?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Personal and group files
- User intent: Choose the correct file area
- Keywords: personal files, group files, group file library, My Files

#### Short answer

Personal files belong to the individual user’s file directory in a space. Their storage location is the user’s home directory or a virtual directory assigned to that user. This area is associated with the individual account rather than a shared group resource.

Group files belong to a shared group folder, also called a group file library. The library is a shared storage location for its members rather than part of any one member’s personal directory. A group library can have an independent storage location, and its content belongs to that shared resource rather than to one member.

#### Version differences

The legacy user guide uses **Group File Folder** and **group folder**. The 8.1.8.0 and later guides commonly use **group file library** and distinguish personal-file directories from group-file-library directories. The terminology changes, but the ownership distinction remains individual directory versus shared library.

#### Important notes

Do not use the visible path name alone to decide ownership. Before moving or deleting content, identify whether the target is your personal directory or a shared group file library. Changing content in a group library can affect the shared resource used by other members.

#### Sources

- `group.md` — “Group Folders”
- `v8180-file.md` — “1. Personal file” and “2. Group file”
- `v8180-group-management.md` — “1. Group file library”

### FAQ-STORAGE-002 | What is a Raysync group folder used for?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Group-folder purpose
- User intent: Collaborate on shared files
- Keywords: group folder, group file library, collaboration, shared directory

#### Short answer

A group folder is shared storage for multi-user collaborative file management. It provides one group file library in which authorized members work with the same shared content. The library can use an independent storage location rather than a member’s personal home directory. It can also be configured with a main directory or virtual directory and with storage-related transfer characteristics such as speed limits and file filtering.

Because it is shared storage, the group library remains a group resource when one member signs out or changes personal files. It is suitable for project, team, or exchange content that must be available to multiple members without placing it in one person’s private directory.

#### Version differences

Legacy documentation calls the resource a group folder and explicitly describes independent storage for each group folder. The 8.1.8.0 and later guide calls it a group file library and continues to describe a shared file directory with configurable main and virtual directories. The storage purpose remains the same across the terminology change.

#### Important notes

Choose a group library for genuinely shared content, not merely as extra personal capacity. Its storage, retention, filtering, or speed characteristics can differ from personal storage. Ask the group administrator which library owns the content before cleanup or migration; this FAQ does not enumerate member operations or portal workflow.

#### Sources

- `group.md` — “Group Folders”
- `space.md` — “5. Group Folder”
- `v8180-group-management.md` — “1. Group file library” and “2. Group permission”

### FAQ-STORAGE-003 | Why can another group member perform a file action that I cannot?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Group member permissions
- User intent: Understand per-member access differences
- Keywords: group permissions, upload, download, delete, rename, member

#### Short answer

Raysync supports different file-operation permissions for members of the same group file library. Administrators can control operations such as listing personal files, downloading, deleting, renaming, creating folders, uploading, creating sync tasks, moving, copying, creating an invite-upload link, and creating a share-download link.

#### Version differences

Legacy space management documents configuration per group member. In the 8.1.8.0 and later navigation, administrators can create **Group permission** definitions and assign them to group file libraries. The visible user outcome is the same: an unavailable button or denied operation may reflect your assigned permission.

#### Important notes

Do not use another member’s account to work around a restriction. If your role requires the action, give the group administrator the group-library name and the exact missing or denied operation.

#### Sources

- `space.md` — “4.2 Space member permissions and transfer configuration” and “5.2 View/Add/Delete group vault members”
- `v8180-group-management.md` — “1.2 View/Add/Delete group vault members” and “2. Group permission”
- `group.md` — “Group Folders”

### FAQ-STORAGE-004 | Why can I upload a new file but not replace a file with the same name?

- Product: Raysync
- Audience: End user
- Applies to: Before 8.1.8.0 legacy space/member settings and 8.1.8.0 and later user-role settings
- Feature: Upload-new-only
- User intent: Understand same-name upload rejection
- Keywords: only upload new files, duplicate name, overwrite, upload blocked

#### Short answer

The destination’s space, user-role, or group-library policy may have **Only upload new files** enabled. That policy allows a newly named file but rejects an upload when the target already contains the same name. The behavior is owned by the policy applied to the destination and account; it is not evidence that the browser plug-in or desktop client failed.

#### Version differences

Before version 8.1.8.0, the legacy space/member settings document **Only upload new files** as an upload policy. For version 8.1.8.0 and later, the user-role guide documents the same behavior as **File upload limit**, while group libraries retain separately assigned group policy. The visible rejection is the same even though policy ownership is organized differently.

#### Important notes

An end user cannot determine from the rejection alone whether the controlling policy is a personal role, space assignment, or group-library policy. Record the destination space/library, path, existing filename, and account, then ask the responsible administrator which policy applies. Do not rename the file merely to bypass an overwrite or retention rule.

#### Sources

- `v8180-user-roles.md` — “User Roles,” “Permission setting description,” “File upload limit”
- `space.md` — “4.2 Space member permissions and transfer configuration,” “Upload file options”
- `v8180-group-management.md` — “1. Group file library” and “2. Group permission”

### FAQ-STORAGE-005 | Why is Raysync blocking files with a particular extension?

- Product: Raysync
- Audience: End user
- Applies to: Legacy versions 6.8.8.2 through before 8.1.8.0, and 8.1.8.0 and later user-role/group-library settings
- Feature: File-format filters
- User intent: Understand extension-based upload rules
- Keywords: file format, whitelist, blacklist, extension, upload filter

#### Short answer

Your personal or group policy may use a transfer file-format allowlist or blocklist. An allowlist permits only configured extensions; a blocklist rejects configured extensions. The legacy guide shows multiple formats separated with semicolons, such as `txt;iso;mp4`.

#### Version differences

The release list introduces group file-library upload format blacklists and whitelists in version 6.8.8.2. For legacy versions from 6.8.8.2 through before 8.1.8.0, the space/member guide documents the allowlist and blocklist behavior. For 8.1.8.0 and later, the user-role guide documents the same model for personal policies, while the current group-management guide confirms filtering for group libraries.

#### Important notes

Changing an extension does not change file content and should not be used to evade policy. Ask the administrator whether the file type is allowed and what approved format or workflow should be used.

#### Sources

- `space.md` — “4.2 Space member permissions and transfer configuration,” “Transfer File Format”
- `v8180-user-roles.md` — “User Roles,” “Permission setting description,” “Transfer file format”
- `v8180-group-management.md` — “1.1 Add/Edit/Delete/Search group file library”
- `release.md` — “v6.8.8.2,” item 7

### FAQ-STORAGE-006 | Why is my upload or download speed limited in a group folder?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.7.8.3 and later group folders
- Feature: Group speed limits
- User intent: Understand a group-specific speed ceiling
- Keywords: speed limit, bandwidth, group folder, upload speed, download speed

#### Short answer

Raysync lets administrators limit upload and download speed for a space member or group file library. The documented default is unlimited, but a configured limit can make group-folder transfers slower than transfers in another area or for another user.

#### Version differences

The release list records group file-library speed limits in version 6.7.8.3. Legacy space management describes upload and download limits, while the 8.1.8.0 and later group-management guide states that group libraries can control transfer speed.

#### Important notes

A configured limit is not necessarily a network fault. Upload and download limits are documented as separate values. Compare only transfers made under the same account, group, and policy. If the observed rate appears inconsistent with the assigned limit, give the administrator the group-library name and task details.

#### Sources

- `space.md` — “4.2 Space member permissions and transfer configuration,” “Upload and download speed limit”
- `v8180-group-management.md` — “1. Group file library”
- `release.md` — “v6.7.8.3,” item 1

### FAQ-STORAGE-007 | What happens when I reach my personal or group storage quota?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.7.8.3 and later when maximum storage capacity is configured
- Feature: Storage quotas
- User intent: Understand why new files are not stored
- Keywords: quota, maximum storage capacity, storage full, upload blocked

#### Short answer

Personal and group quotas apply to different owners. A personal quota is assigned to a user in the current space; in 8.1.8.0 and later, the current user-role guide calls this **Maximum storage**. A group quota belongs to the shared group file library rather than to one member. The release history states that users and group file libraries support maximum storage capacity. When a configured limit is exceeded, new files are no longer stored; existing files are not described as being automatically removed merely because the quota is exceeded.

#### Version differences

User and group-library maximum capacity was added in version 6.7.8.3. For 8.1.8.0 and later, `v8180-user-roles.md` explicitly documents the per-user limit. Group-library storage remains a shared group concern; the current storage guide separately tracks personal-folder and group-library storage statistics.

#### Important notes

First identify whether the destination is your personal files or a group file library. Freeing personal space does not document that a group-library quota will change, and deleting another member’s shared data may cause data loss. Ask the administrator or group administrator whether authorized cleanup, quota expansion, or a different target is appropriate. Object-storage accounting may depend on administrator statistics settings.

#### Sources

- `v8180-user-roles.md` — “User Roles,” “Permission setting description,” “Maximum storage”
- `space.md` — “4.2 Space member permissions and transfer configuration,” “Maximum storage capacity,” and “7. Space statistics”
- `v8180-storage.md` — “2. Statistics period”
- `release.md` — “v6.7.8.3,” item 2

### FAQ-STORAGE-008 | Why is a path hidden or unavailable in my Raysync files?

- Product: Raysync
- Audience: End user
- Applies to: Legacy versions 6.7.8.0 through before 8.1.8.0, and 8.1.8.0 and later user-role path settings
- Feature: Forbidden and allowed paths
- User intent: Understand path-level visibility and operation limits
- Keywords: forbidden path, allowed path, hidden folder, access denied

#### Short answer

The administrator may have configured a forbidden access path or an allowed access path. A forbidden path is hidden and cannot be created in, deleted, renamed, copied, moved, uploaded to, or downloaded from. With allowed paths, only the configured files or folders are visible, and operations outside them are unavailable.

#### Version differences

Allowed access paths are listed in the version 6.7.8.0 release. For legacy versions from 6.7.8.0 through before 8.1.8.0, the space/member guide describes both forbidden and allowed path controls. For 8.1.8.0 and later, the user-role guide documents the same controls for personal roles. Group-library path policy remains separately assignable.

#### Important notes

The absence of a path can be intentional security policy, not data loss. Do not try alternate clients or path spellings to bypass it. Ask the administrator to confirm your authorized path scope.

#### Sources

- `space.md` — “4.2 Space member permissions and transfer configuration,” “Forbidden access path” and “Allowed access path”
- `v8180-user-roles.md` — “User Roles,” “Permission setting description,” “Forbidden path” and “Allowed access path”
- `release.md` — “V6.7.8.0,” item 9
- `v8180-group-management.md` — “1.1 Add/Edit/Delete/Search group file library”

### FAQ-STORAGE-009 | What is a virtual directory in Raysync?

- Product: Raysync
- Audience: End user
- Applies to: Version 5.0.6.8 and later
- Feature: Virtual directories
- User intent: Work with an additional mapped file location
- Keywords: virtual directory, alias, mapped path, home directory

#### Short answer

A virtual directory is an administrator-added directory that appears in your file area under an alias and maps to a valid path in configured storage. A user can view, transfer, and operate files in it subject to permissions. Multiple virtual directories are supported.

#### Version differences

Virtual directories in the user directory were added in version 5.0.6.8. The legacy spaces guide describes the alias and mapped path. The 8.1.8.0 and later storage guide says storage configuration supplies home and virtual directories for users and group libraries; version 8.1.8.2 optimized virtual-path interaction.

#### Important notes

A virtual directory is not necessarily a copy of the data. Also, the user guide states that a virtual directory cannot be renamed from the client. Ask the administrator if its alias or mapping appears wrong.

#### Sources

- `space.md` — “4.2 Space member permissions and transfer configuration,” “Virtual Directory”
- `v8180-storage.md` — “1. Storage configuration”
- `files.md` — “2.3 File operations,” “Rename”
- `release.md` — “v5.0.6.8,” item 3, and “v8.1.8.2,” item 2

### FAQ-STORAGE-010 | What happens when the storage behind Raysync is exhausted?

- Product: Raysync
- Audience: End user
- Applies to: All documented storage types; underlying-storage exhaustion is not version-bounded by the supplied sources
- Feature: Underlying storage exhaustion
- User intent: Escalate a suspected backend-capacity problem without assuming behavior
- Keywords: storage exhausted, backend storage, upload failure, capacity, undocumented behavior

#### Short answer

The supplied sources do not specify what an end user sees when the physical or object storage behind Raysync is exhausted. They document supported storage types, storage configuration, and statistics, but they do not define a reliable error message, automatic fallback, retry behavior, or recovery procedure for backend-capacity exhaustion. Therefore, an upload or file-operation error must not be labeled as underlying storage exhaustion from these sources alone.

#### Version differences

Legacy documentation describes storage within spaces; the 8.1.8.0 and later guide documents local and several object-storage types in the later storage guide family. Neither guide family supplies a version boundary or end-user behavior for exhaustion of the underlying storage.

#### Important notes

Preserve the exact error, target space/library and path, task time, file size, and whether other operations still work. Contact the administrator to check backend capacity and storage health. Do not repeatedly retry a large upload or delete shared data to “make room” without authorization; the sources do not establish that either action is the correct recovery.

#### Sources

- `storage.md` — “Configure Storage”
- `space.md` — “1. Space Storage Configuration” and “7. Space statistics”
- `v8180-storage.md` — “1. Storage configuration” and “2. Statistics period”

### FAQ-STORAGE-011 | Which storage types can be visible through Raysync?

- Product: Raysync
- Audience: End user
- Applies to: Current storage documentation
- Feature: Visible storage types
- User intent: Understand where portal files may be stored
- Keywords: local storage, OSS, S3, Azure Blob, Google Cloud Storage

#### Short answer

Depending on administrator configuration, files exposed through a personal or group directory can use local storage, Alibaba Cloud OSS, Amazon S3, S3-compatible storage, Azure Blob, or Google Cloud Storage. Raysync can configure multiple storages for the home and virtual directories of users and group file libraries.

#### Version differences

The legacy spaces guide and the 8.1.8.0 and later storage guide list the same major local and object-storage families. The underlying endpoint, bucket, credentials, and server path remain administrator prerequisites and are intentionally outside this end-user FAQ.

#### Important notes

The portal path or virtual-directory alias may not reveal the backend storage type. Different storage types can also have different accounting or feature limits; for example, the legacy guide says quota statistics count local storage by default unless object-storage statistics are enabled.

#### Sources

- `storage.md` — “Configure Storage”
- `v8180-storage.md` — “1. Storage configuration” and “2. Statistics period”
- `space.md` — “1. Space Storage Configuration” and “7. Space statistics”

### FAQ-STORAGE-012 | Can one Raysync deployment have multiple spaces?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.2.8.0 and later
- Feature: Multiple spaces
- User intent: Understand separate work areas
- Keywords: multiple spaces, default space, membership, storage

#### Short answer

Yes. Multiple spaces were added in version 6.2.8.0. A deployment has a default space, and administrators can create additional spaces, assign members and administrators, configure storage, create group folders, and apply space access restrictions. A newly created user is a member of the default space according to the legacy spaces guide.

#### Version differences

Legacy documentation groups space storage, members, group folders, and access restrictions under **Spaces**. In the 8.1.8.0 and later documentation, storage and group management appear in separate **Configuration** and **File** areas, while the quick-start storage guide still states that multiple spaces can use different storage.

#### Important notes

Seeing one space does not establish membership in every other space; membership can differ by account. If a required work area is missing, provide its name to an administrator so your membership can be checked.

Additional spaces can be configured with storage different from the deployment’s default space.

#### Sources

- `release.md` — “v6.2.8.0,” item 1
- `space.md` — introduction and “Manage Space Members”
- `storage.md` — “Configure Storage”

### FAQ-STORAGE-013 | Are files and permissions isolated between Raysync spaces?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.2.8.0 and later
- Feature: Space isolation
- User intent: Understand access boundaries between spaces
- Keywords: space isolation, membership, access restriction, separate storage

#### Short answer

Spaces are separately administered work areas: administrators assign members, storage, group folders, access restrictions, and file-delivery settings per space. As an end user, you see and operate within the spaces, personal directories, and group libraries made available to your account; membership or permission in one space does not document permission in another.

#### Version differences

Multiple spaces began in version 6.2.8.0. The legacy spaces guide presents per-space membership and security access restrictions directly. The 8.1.8.0 and later storage guide confirms that storage supplies user and group-library directories in a space and can include multiple storages.

#### Important notes

“Isolation” here describes administrative membership, storage, and access boundaries; the source does not claim a particular low-level tenant-isolation architecture. If content appears in the wrong space or an unexpected space is visible, stop modifying files and report the exact space and path to the administrator.

#### Sources

- `space.md` — introduction, “Manage Space Members,” “Group Folder,” and “Security Access Restrictions”
- `storage.md` — “Configure Storage”
- `v8180-storage.md` — “1. Storage configuration”
- `release.md` — “v6.2.8.0,” item 1
