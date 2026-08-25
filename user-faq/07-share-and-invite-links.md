### FAQ-LINK-001 | How do I create a share-download link?

- Product: Raysync
- Audience: End user
- Applies to: Base share-download flow in all documented versions; download-time and scheduled notification controls from version 6.7.8.2
- Feature: Share-download link
- User intent: Share files for download
- Keywords: share-download link, share files, recipient download

#### Short answer

Create a share-download link from selected files or folders, then distribute the generated link to intended download recipients.

#### Prerequisites

- You can access the files or folders and have permission to share them.
- If Raysync will email the link, the assigned administrator or personal mail service must already be configured.

#### Steps

1. Select one or more files or folders and choose **Share to download**.
2. Choose the sharing scope and configure download permission and download times.
3. Configure any available recipient email restriction, password, expiration time, and file alias.
4. Configure email, scheduled delivery, and download notifications if needed.
5. Select **Create**, then copy or send the generated link and access password.

#### Version differences

Download-time limits and scheduled link-sharing notifications were added in version 6.7.8.2. Specified-recipient email protection is recorded in version 6.8.8.2 and again in version 8.1.8.3; the sources do not establish version 8.1.8.3 as its sole introduction date. In version 8.1.8.0 and later, user portal link lists also support filtering.

#### Important notes

Choose **Anyone with the link** only when broad access is acceptable. Use organization login, recipient email, password, and expiration controls for more restricted sharing.

#### Sources

- `share-link.md` — “Create share link”
- `cloud.md` — “Create share link”
- `release.md` — “v6.7.8.2” and “v6.8.8.2”
- `release.md` — “v8.1.8.3” and “v8.1.8.0”

### FAQ-LINK-002 | How do I create an invite-upload link?

- Product: Raysync
- Audience: End user
- Applies to: Base invite-upload flow in all documented versions; new-folder support recorded in versions 6.2.8.0 and 6.3.8.0; scheduled notification and deletion permission from version 6.7.8.2
- Feature: Invite-upload link
- User intent: Invite others to upload
- Keywords: invite-upload link, upload directory, Create Link

#### Short answer

Create the invite-upload link from the directory that should receive the uploaded content.

#### Prerequisites

- You can access the destination folder and have permission to create an invitation.
- If Raysync will email the link, the assigned administrator or personal mail service must already be configured.

#### Steps

1. Open the destination folder and choose **Invite to upload**.
2. Choose the invitation scope and configure any available recipient email restriction.
3. Set the password, expiration time, and **Allow deletion** permission as required.
4. Configure email, scheduled delivery, and upload notifications if needed.
5. Select **Create Link**, then use **Copy Link and Password** or the configured email option.

#### Version differences

Invite-upload creation of a new folder is recorded in both v6.2.8.0 and v6.3.8.0. Scheduled link notification and recipient deletion permission were added in v6.7.8.2. Specified-recipient email protection is recorded in v6.8.8.2 and again in 8.1.8.3; the sources do not prove a single introduction date. Version 8.1.8.0 added filtering of invite-link lists and admin-side link deletion.

#### Important notes

The invite page may show all files and folders already in the invited directory. Choose the destination carefully and grant deletion only when the recipient is trusted.

#### Sources

- `invitation-link.md` — “Create an invite to upload link”
- `cloud.md` — “Create invite link”
- `release.md` — “v6.2.8.0,” “v6.3.8.0,” “v6.7.8.2,” and “v6.8.8.2”
- `release.md` — “v8.1.8.3” and “v8.1.8.0”

### FAQ-LINK-003 | How does a recipient open a share-download link?

- Product: Raysync
- Audience: End user
- Applies to: Browser share access generally; desktop-client link handling from version 8.1.8.4
- Feature: Share-download access
- User intent: Download shared files
- Keywords: open share link, password, download

#### Short answer

Open the link, complete its access checks, and download from the shared file list.

#### Prerequisites

- Obtain the share-download link and its password, if one is required.
- Have the required organization account or specified email login when the link is restricted.

#### Steps

1. Open the share-download link in a browser.
2. Enter the password if prompted and select **Log in**.
3. Complete any organization or specified-email authentication.
4. In the shared file list, select the download control for the required files.

#### Desktop-client alternative for version 8.1.8.4 and later

1. Copy the share-download link and open the desktop client.
2. Let the client detect the clipboard link, or enter the link manually if detection does not find it.
3. Start the download from the desktop client.

#### Version differences

Desktop-client upload/download through Raysync links was added in 8.1.8.4. Browser access remains documented for earlier versions.

#### Important notes

The creator may disable downloads, limit download counts, expire the link, bind it to the first device, or restrict it to specified recipients. A valid URL alone may therefore be insufficient.

#### Sources

- `share-link.md` — “Access the share link”
- `files.md` — “File Upload and Download through Raysync Links Supported”
- `release.md` — “v8.1.8.4”

### FAQ-LINK-004 | How does a recipient open an invite-upload link?

- Product: Raysync
- Audience: End user
- Applies to: Browser invite access generally; new-folder support recorded in versions 6.2.8.0 and 6.3.8.0; desktop-client link handling from version 8.1.8.4
- Feature: Invite-upload access
- User intent: Upload through an invitation
- Keywords: open invite link, upload, new folder

#### Short answer

Open the invitation, complete its access checks, and upload into the displayed destination directory.

#### Prerequisites

- Obtain the invite-upload link and its password, if one is required.
- Have the required organization account or specified email login when the invitation is restricted.

#### Steps

1. Open the invite-upload link in a browser.
2. Enter the password if prompted and select **Log in**.
3. Complete any organization or specified-email authentication.
4. Select **Upload** and choose the files to add.
5. If **New Folder** is available, create a folder first and upload into it as needed.

#### Version differences

Invite-upload links are recorded as gaining new-folder creation in v6.2.8.0 and again in v6.3.8.0. From 8.1.8.4, the desktop client can detect a copied Raysync link and initiate the corresponding upload. Browser access is documented generally.

#### Important notes

Deletion is available to recipients only if the creator enabled **Allow deletion**. Visibility of existing content does not by itself grant deletion permission.

#### Sources

- `invitation-link.md` — “Visit the invite to upload link”
- `files.md` — “File Upload and Download through Raysync Links Supported”
- `release.md` — “v6.2.8.0” and “v6.3.8.0,” invite new-folder support
- `release.md` — “v8.1.8.4”

### FAQ-LINK-005 | How do passwords and expiration dates protect a Raysync link?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Link access controls
- User intent: Secure a link
- Keywords: link password, expiration time, access control

#### Short answer

A password makes recipients verify the correct password before opening a share-download or invite-upload link. An expiration time limits how long the link remains valid. These controls can be combined with organization-only scope or specified-recipient email protection.

The documented creation flows generate an access password by default. The creator can copy the link and password and send them to the intended recipient.

#### Version differences

Password and expiration controls are present throughout the cited link guides. Specified-recipient email protection is recorded in v6.8.8.2 and again in 8.1.8.3; the sources do not prove a single introduction date.

#### Important notes

A password does not distinguish recipients if everyone receives the same credentials. For sensitive content, also restrict the scope or specify recipient emails. When possible, send the password separately from the link; the administrator controls whether share-link emails carry them together or separately.

#### Sources

- `share-link.md` — “Create share link,” password and expiration options
- `invitation-link.md` — “Create an invite to upload link,” password and expiration options
- `local-user.md` — “Share download email notification”
- `release.md` — “v6.8.8.2” and “v8.1.8.3,” specified-recipient email protection

### FAQ-LINK-006 | Can I restrict a link to specific recipient email addresses?

- Product: Raysync
- Audience: End user
- Applies to: Recorded in version 6.8.8.2 and again in version 8.1.8.3
- Feature: Recipient email protection
- User intent: Limit link access by email
- Keywords: specified email, recipient protection, login

#### Short answer

Yes. Add the intended email address when creating the link. Only a user with the specified email address can satisfy that email-match restriction. If no specified email is configured, only the email-match restriction is removed; the selected scope, organization login, password, expiration, device binding, and download permissions or limits still apply when configured.

This control applies to both share-download and invite-upload links, but the allowed action remains different: download for a share link, upload for an invitation link.

#### Version differences

The release list records specified-recipient email protection in v6.8.8.2 and again in 8.1.8.3. Because both entries describe the capability, the supplied sources do not prove a single introduction date. Use the control when it is present in your deployed version.

#### Important notes

Email restriction requires authentication with the matching address. It does not replace the link's other configured access and download controls.

#### Sources

- `invitation-link.md` — “Support specify the recipient's email to protect shared content”
- `share-link.md` — “Specify the email to access”
- `release.md` — “v6.8.8.2,” specified email access
- `release.md` — “v8.1.8.3”

### FAQ-LINK-007 | How do I find internal members when choosing link recipients?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.3 and later
- Feature: Internal member search
- User intent: Select an organization recipient
- Keywords: fuzzy search, internal member, account, email, name

#### Short answer

When selecting people within your organization, enter part of the user's account, email address, or name. Raysync's fuzzy search accepts partial or imprecise keywords and returns closely matching members for selection.

Use this search while setting an organization-restricted recipient or notification audience. It does not change a share-download link into an invite-upload link or vice versa.

#### Version differences

Internal-member fuzzy search was added in 8.1.8.3. Earlier versions do not have this documented search behavior.

#### Important notes

Review the matched account and email before creating the link, especially when several people have similar names. Fuzzy matching is a selection aid, not an access-control substitute; configure scope and recipient email restrictions as needed.

#### Sources

- `invitation-link.md` — “Internal member fuzzy search”
- `release.md` — “v8.1.8.3,” Internal member fuzzy search

### FAQ-LINK-008 | Can Raysync email the link to recipients for me?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Link email notification
- User intent: Send a link by email
- Keywords: email recipients, notification, mail settings

#### Short answer

Yes. Enable **Email notifications to partners** while creating a share-download or invite-upload link. The UI also includes **Notify to recipients**, described as sending a separate identical message to a “private recipient” with an option to include the access password. The supplied documentation does not define “private recipient” or explain how that party is designated, so follow the fields shown in your deployed interface rather than assuming a recipient type.

By default, email uses the administrator-configured mail service. If the administrator assigns your personal mailbox as the sender, configure it in **Personal Center > Mail Settings** first.

#### Version differences

The cited sources do not document a user-visible version difference in this email-notification option. Email delivery still requires an administrator-configured mail service or an assigned personal mailbox.

#### Important notes

Mail delivery depends on valid server or personal mail settings. If email delivery is unavailable, the invitation guide documents **Copy Link and Password** for manual delivery. The sources do not specify what result the creation form displays when email configuration is missing.

#### Sources

- `share-link.md` — “Email notifications to partners”
- `invitation-link.md` — “Email notifications to partners”
- `invitation-link.md` — “Copy Link and Password”
- `profile.md` — “Mail Settings”
- `v8180-notification.md` — “Email configuration”

### FAQ-LINK-009 | Can the link and password be sent in separate emails?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.0.0.8 and later, when enabled by account configuration
- Feature: Share email security
- User intent: Separate credentials
- Keywords: separate password email, link email, share notification

#### Short answer

Yes, for share-download email notification. Raysync account configuration supports either sending the link and password in one email or sending them in different emails. This choice is set for the user by an administrator rather than by the recipient.

The **Notify to recipients** option can include or omit the access password. The supplied documentation calls its destination a “private recipient” but does not define that term or explain how the destination is selected.

#### Version differences

Sending the share link and password in separate emails was added in version 6.0.0.8. The same one-email versus separate-email choice appears in both the earlier local-user guide and the guide for version 8.1.8.0 and later.

#### Important notes

The cited account setting is named **Share download email notification**. Do not assume that it changes every invite-upload mail workflow. If the option is unavailable, ask the administrator which delivery policy is assigned to your account.

#### Sources

- `local-user.md` — “Share download email notification”
- `v8180-users.md` — “Share download email notification”
- `share-link.md` — “Notify to recipients”
- `invitation-link.md` — “Notify to recipients”
- `release.md` — “v6.0.0.8,” separate link and password emails

### FAQ-LINK-010 | How do share-download limits work?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.7.8.2 and later
- Feature: Share download limits
- User intent: Limit link use
- Keywords: download times, disable download, organization scope

#### Short answer

The creator can turn downloads off or set a number of download times. For **Anyone with the link**, the documented count is shared across all visitors to the link. For **Only people in your organization**, the limit applies individually to each visiting user.

The limit is part of the share-download link settings that the link creator chooses. Recipients cannot increase or reset it.

#### Version differences

Download-time limits on share links were added in v6.7.8.2. Version 8.1.8.0 added filtering for share/invite links in the user portal.

#### Important notes

Turning off **Allow users to download** prevents file download even if the link opens successfully. Download limits belong to share-download links; invite-upload links instead control upload and optional deletion.

#### Sources

- `share-link.md` — “Create share link,” download permission and Download times
- `release.md` — “v6.7.8.2,” share-link download times
- `release.md` — “v8.1.8.0,” user portal link filtering

### FAQ-LINK-011 | Can I schedule when Raysync emails a link?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.7.8.2 and later
- Feature: Scheduled link notification
- User intent: Send link notification later
- Keywords: Send regularly, scheduled email, notification time

#### Short answer

Yes. Enable **Send regularly** during share-download or invite-upload link creation and set the desired time. Raysync sends the email notification at that time, telling recipients to open the link.

The timer schedules notification delivery; it is not described as delaying creation of the link itself. Configure the link's expiration time so the emailed link will still be valid when the scheduled message arrives.

#### Version differences

Scheduled link-sharing notification was added in v6.7.8.2. Current share and invitation guides expose it as **Send regularly**.

#### Important notes

The administrator's mail service or your assigned personal mail service must be configured. Scheduled email is separate from transfer scheduling and does not schedule a recipient's upload or download.

#### Sources

- `share-link.md` — “Send regularly”
- `invitation-link.md` — “Send regularly”
- `notification.md` — email configuration prerequisite
- `v8180-notification.md` — “Email configuration”
- `release.md` — “v6.7.8.2,” scheduled link-sharing notification

### FAQ-LINK-012 | What does binding a share link to the first device do?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions when enabled by an administrator
- Feature: First-device binding
- User intent: Restrict device access
- Keywords: first device, device binding, unbind link

#### Short answer

When first-device binding is enabled, a share-download link can be opened only on the first device that accesses it. A second device receives a message that the link is already bound. If access must move to another device, ask an authorized administrator to unbind the link.

#### Version differences

The cited sources do not document a user-visible version difference in first-device binding. Availability depends on administrator enablement.

#### Important notes

This control is documented for share-download links, not invite-upload links. It must first be enabled by the administrator, so an end user may not see the option.

#### Sources

- `share-link.md` — “Share link management,” device binding
- `configuration.md` — “Link,” Bind the first device
- `collaboration.md` — “Share to download”
- `v8180-collaboration.md` — “Share to download”

### FAQ-LINK-013 | What does Allow deletion mean on an invite-upload link?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.7.8.2 and later
- Feature: Invitation deletion permission
- User intent: Control recipient file deletion
- Keywords: allow deletion, invite upload, destructive permission

#### Short answer

**Allow deletion** lets people using the invite-upload link delete files in the invitation directory. Without it, recipients can upload but do not receive this deletion permission from the link.

The invitation view may display all files and folders in the selected directory, which makes careful destination selection important.

#### Version differences

Allowing external users to delete files through an invite-upload link was added in v6.7.8.2.

#### Important notes

**Destructive permission:** enabling deletion can remove existing or newly uploaded content from the invited directory. Grant it only to trusted recipients and only for a directory where such deletion is acceptable. This setting belongs to invite-upload links; it is unrelated to the share-download option that allows or blocks downloads.

#### Sources

- `invitation-link.md` — “Create an invite to upload link,” Allow deletion
- `invitation-link.md` — “Visit the invite to upload link”
- `release.md` — “v6.7.8.2,” invite-link deletion permission

### FAQ-LINK-014 | Can I disable a link and enable it again later?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.3 and later for documented re-enable behavior
- Feature: Link status management
- User intent: Temporarily stop link access
- Keywords: disable link, enable link, inactive link

#### Short answer

Yes. In the link-management list, select the link and disable it when it should no longer be usable. A disabled link is inaccessible. To restore the same link's validity, select it and enable it again.

The enable/disable guide refers to created sharing links for upload or download, so check the correct management list: **Share to download** for download links and **Invite to upload** for upload invitations.

#### Version differences

Enable/disable shared-link functionality is listed in the 8.1.8.3 release. Earlier guides document canceling links but do not explicitly document re-enabling them.

#### Important notes

Disabling is temporary. Canceling or deleting a link is a different management action and should not be assumed reversible.

#### Sources

- `share-link.md` — “Enable/Disable Shared Link Functionality”
- `release.md` — “v8.1.8.3,” Enable/Disable Shared Link Functionality
- `invitation-link.md` — “Manage invite to upload links”

### FAQ-LINK-015 | What is the difference between canceling and deleting a link?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; administrator deletion recorded in version 8.1.8.0
- Feature: Link lifecycle management
- User intent: End or remove a link
- Keywords: cancel link, delete link, link record

#### Short answer

As an end user, cancel a share-download link to make it inaccessible or cancel an invite-upload link to end the invitation. The user guides document these cancellation actions. Deleting the link record requires an authorized administrator and is not an end-user procedure.

#### Version differences

User portal filtering of share and invite links was added in version 8.1.8.0. Administrator-side deletion is also recorded for that version, but it does not change the end-user cancellation flow.

#### Important notes

The sources do not document recovery after administrator deletion. If you only need to stop end-user access temporarily and your version exposes disable/enable, use that status control. Cancel the correct link type: an invitation affects uploads, while a share affects downloads.

#### Sources

- `share-link.md` — “Share link management”
- `invitation-link.md` — “Manage invite to upload links”
- `collaboration.md` — invite and share management
- `v8180-collaboration.md` — invite and share management
- `release.md` — “v8.1.8.0”

### FAQ-LINK-016 | What link activity and records can I review as an end user?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; user portal list filtering from version 8.1.8.0
- Feature: Link activity and records
- User intent: Review user-visible link activity
- Keywords: activity records, download notifications, upload notifications, link filtering

#### Short answer

As an end user, use your share-download or invite-upload management list to review and control links you created. Link creation can request notifications when a download or upload starts and completes. From 8.1.8.0, the user portal supports filtering share and invite links, making it easier to find your own link entries.

#### Version differences

User portal filtering for share and invite link lists was added in version 8.1.8.0. The current link guides also document optional notifications when a download or upload starts and completes.

#### Important notes

The sources do not document a full per-action audit trail for ordinary users. If you need records beyond your user-visible link list and configured notifications, contact an administrator; Collaboration record review is an administrator-side prerequisite.

#### Sources

- `collaboration.md` — “Invite to upload” and “Share to download”
- `v8180-collaboration.md` — “Invite to upload” and “Share to download”
- `share-link.md` — “Download notifications”
- `invitation-link.md` — “Upload notification”
- `release.md` — “v8.1.8.0,” user portal link filtering
