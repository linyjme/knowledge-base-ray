### FAQ-ACCOUNT-001 | How do I view and update my personal information?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Personal Center
- User intent: View or edit profile details
- Keywords: personal information, real name, Personal Center

#### Short answer

In the user portal, select your user name in the upper-right corner, then open **Personal Center**. Open **User Message** to view and edit the personal fields documented for end users, including your real name and login email.

Your account number is different from these editable profile fields. The administrator-side user documentation states that the account number cannot be modified after the account is created.

#### Version differences

The cited sources do not document a user-visible version difference for these **Personal Center** steps.

#### Important notes

Some account properties—permissions, home directory, role, status, validity, and transfer settings—are administrator-controlled and are not editable from Personal Center.

#### Sources

- `profile.md` — “User Center” and personal information (source heading: “User Massage”)
- `local-user.md` — “Add user,” Account number
- `v8180-users.md` — “Add user,” Account number

### FAQ-ACCOUNT-002 | How do I change my Raysync password while signed in?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Password management
- User intent: Change a known password
- Keywords: update password, Personal Center, login password

#### Short answer

Select your user name in the upper-right corner, open **Personal Center**, and select **Update Password**. Enter the required current and new password information shown by the form, then save the change. Use the new password the next time you log in.

If an administrator requires a password reset on first login, Raysync opens the reset-password page before normal access. Complete that prompt and continue with the new password.

#### Version differences

The cited sources do not document a user-visible version difference for signed-in password changes.

#### Important notes

The supplied documentation does not state a universal password rule for signed-in changes through **Update Password**. Follow the validation shown by your deployment or the policy provided by your administrator.

#### Sources

- `profile.md` — “Update Password” and “User login”

### FAQ-ACCOUNT-003 | How do I update the email address used for login and recovery?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Login email
- User intent: Change account email
- Keywords: login email, User Message, password recovery

#### Short answer

Open your user-name menu, select **Personal Center**, and open **User Message**. Edit the login email and save it. Raysync supports email login, and the forgot-password workflow sends its verification code to the account's login email.

#### Version differences

The cited sources do not document a user-visible version difference for editing the login email.

#### Important notes

Make sure the new address is valid and accessible before depending on password recovery. The login email is separate from the SMTP sender settings in **Mail Settings**. Changing one does not configure the other. If profile editing is restricted in your deployment, ask an administrator to update the account record.

#### Sources

- `profile.md` — personal information (source heading: “User Massage”) and “Forget Password”
- `local-user.md` — “Add user,” Email
- `v8180-users.md` — “Add user,” Email

### FAQ-ACCOUNT-004 | What are personal mail settings, and when do I need them?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions when assigned a personal mailbox sender
- Feature: Personal mail settings
- User intent: Configure notification sender email
- Keywords: Mail Settings, SMTP sender, share notification

#### Short answer

Open **Personal Center > Mail Settings** to configure the sender email service used for share-download and invite-upload notification messages. You need this only when an administrator has assigned your account to send with a user-configured mailbox.

If your account is set to use the administrator-configured mailbox, notification email uses the system mail service instead and personal sender configuration is not required.

#### Version differences

The same two sender choices are documented in the current and earlier account guides.

#### Important notes

These settings control outgoing notification mail, not your login email. Valid system or personal mail configuration is required for successful email delivery.

#### Sources

- `profile.md` — “Mail Settings”
- `local-user.md` — “Mailbox sender”
- `v8180-users.md` — “Mailbox sender”
- `notification.md` — email prerequisite

### FAQ-ACCOUNT-005 | What must be configured before I can recover a forgotten password?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.2.8.0 and later
- Feature: Password recovery
- User intent: Determine password-recovery prerequisites
- Keywords: forgot password, verification code, system mail

#### Short answer

Password recovery requires both an accessible login email and a configured Raysync system mail service. Raysync uses that mail service to send the required verification code to the login email.

#### Prerequisites

- Your account has an accessible login email.
- The administrator has configured the Raysync system mail service.

#### Version differences

User password recovery was added in version 6.2.8.0.

#### Important notes

Without both prerequisites, Raysync cannot deliver the documented recovery verification code. Contact an administrator to correct the account email or system mail configuration.

#### Sources

- `profile.md` — “Forget Password”
- `notification.md` — email configuration prerequisite
- `v8180-notification.md` — “Email configuration”
- `release.md` — “v6.2.8.0,” user password retrieval

### FAQ-ACCOUNT-006 | What does a locked, disabled, or expired account status mean?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Account status
- User intent: Understand unavailable account status
- Keywords: locked account, disabled account, expired account, administrator

#### Short answer

An administrator can lock or disable a user account. A disabled account cannot log in. An account can also become unavailable when its account-validity period or password-validity period expires, depending on administrator configuration.

There is no documented end-user unlock control. Ask an administrator to check the account status and unlock or re-enable it when appropriate.

#### Version differences

The current and earlier account guides document administrator lock/unlock and disabled status. The current guide also documents unavailability after password or account expiration.

#### Important notes

Do not assume every login failure means a lock: an incorrect password, IP whitelist, or other authentication requirement can also prevent login. The sources do not provide an end-user diagnostic procedure beyond using correct credentials and contacting the administrator for controlled settings.

#### Sources

- `local-user.md` — “Lock/unlock user” and account status/validity
- `v8180-users.md` — “Lock/unlock user,” account status, password expiration, account validity
- `profile.md` — “User login”

### FAQ-ACCOUNT-007 | Can I view or change my assigned transfer priority?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.6 and later
- Feature: Transfer priority
- User intent: Check or change transfer priority
- Keywords: low, medium, high, bandwidth allocation

#### Short answer

Transfer priority is assigned through your user role by an administrator when the server-wide priority feature is enabled. The documented levels are **Low**, **Medium**, and **High**, with **Medium** as the role default. The supplied sources do not identify an end-user control for viewing or changing the assigned level.

The source states that a user's bandwidth “will be shared with their inviter/sharer,” but it does not define the allocation direction, participants, or calculation. Do not infer a specific bandwidth split from that sentence; ask the administrator how the configured deployment applies it.

#### Version differences

User transfer priority was added in version 8.1.8.6. Administrators enable the feature and assign the priority through user roles; earlier versions do not document this role priority.

#### Important notes

Priority is not an end-user setting in the supplied documentation. Ask an administrator to confirm your assigned role or request a change.

#### Sources

- `release.md` — “v8.1.8.6,” Supports setting user transfer priority
- `v8180-transfer.md` — “Transfer,” Transfer priority
- `v8180-user-roles.md` — “Transfer priority”

### FAQ-ACCOUNT-008 | Can my account belong to more than one space?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.2.8.0 and later
- Feature: Space membership
- User intent: Access multiple spaces
- Keywords: multiple spaces, space member, default space

#### Short answer

Space membership is assigned by administrators. A new user is a member of the default space, and space administrators can add or remove members in other spaces. The cited sources do not document a self-service **Join space** action, so request membership from the relevant administrator.

When your account is added to another space, that space can have its own storage, home or virtual directories, access restrictions, permissions, speed limits, and group folders.

#### Version differences

Multiple-space support was added in version 6.2.8.0. The end-user consequence is membership-based access to each assigned space.

#### Important notes

Being able to log in does not automatically grant access to every space. Access comes from membership and the settings assigned within that space.

#### Sources

- `space.md` — introduction and “Manage Space Members”
- `v8180-users.md` — “Users”
- `v8180-user-roles.md` — “User Roles”
- `release.md` — “v6.2.8.0,” multiple spaces

### FAQ-ACCOUNT-009 | Why can I have different permissions in different spaces?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Space permissions
- User intent: Understand permission differences
- Keywords: space permissions, allowed path, speed limit, sync permission

#### Short answer

Permissions and transfer configuration can be assigned per space membership. A space administrator can configure your home and virtual directories, forbidden and allowed paths, file-operation permissions, upload rules, speed limits, transfer formats and filters, notifications, and storage limit for that space.

Therefore, the same account may be able to upload, sync, invite, or share in one space but not another. The visible files can also differ because allowed and forbidden paths are space-specific.

#### Version differences

The permission model differs across documented versions, but the user-visible result is the same: assigned permissions can differ by space.

#### Important notes

These controls are intentional access rules, not necessarily a client error. If access is unexpected, identify the affected space and ask its administrator to review your membership or role.

#### Sources

- `space.md` — “Space member permissions and transfer configuration”
- `v8180-user-roles.md` — “Permission setting description”
- `v8180-permission-setting.md` — default user and group roles

### FAQ-ACCOUNT-010 | How does group-folder membership affect what I can see and do?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Group folders
- User intent: Use shared group storage
- Keywords: group folder, membership, collaborative files

#### Short answer

The **Group File Folder** page shows only the group file libraries associated with your account. Membership determines which libraries appear, and your assigned group-folder permissions determine which actions are available after you open one.

Group-folder membership is separate from general space membership, and different members of the same group folder can receive different permissions.

#### Version differences

The cited sources do not document a user-visible version difference for opening an assigned group folder.

#### Important notes

If a group folder or action is missing, your account may not have the required membership or assigned permission.

#### Sources

- `group.md` — “Group Folders”
- `space.md` — “Group Folder” and group-folder members (source heading: “View/Add/Delete group cault members”)
- `v8180-permission-setting.md` — default group roles

### FAQ-ACCOUNT-011 | Why can’t I change a permission, sync frequency, or other restricted setting?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Administrator-controlled settings
- User intent: Understand locked controls
- Keywords: restricted setting, role, external authentication, sync frequency

#### Short answer

Some settings are assigned by the administrator or an external identity service and are intentionally unavailable to end users. Examples include file-operation permissions, allowed or forbidden paths, sync-filter controls, sync-task frequency, transfer priority, menu visibility, storage limits, and P2P permission.

For Raysync-managed authentication, administrators and assigned roles control access. For system or external-HTTP-controlled permissions, the Raysync default-permission setting does not take effect because the external service controls access.

#### Version differences

The permission model differs across documented versions, but restricted controls remain administrator- or identity-provider-managed rather than end-user settings.

#### Important notes

If a field is locked or absent, changing the client will not override the assigned policy. Ask the administrator which role, space rule, or external authentication policy applies to your account.

#### Sources

- `local-user.md` — user permissions, filtering, sync frequency, and P2P controls
- `v8180-user-roles.md` — permission, priority, filtering, frequency, and menu controls
- `default-permission.md` — default authentication permissions
- `v8180-permission-setting.md` — default roles and external control
