### FAQ-VERSION-001 | How can I identify which Raysync version I am using?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Version identification
- User intent: Find the installed client version before following instructions
- Keywords: version number, About Raysync, client version, build

#### Short answer

Use this standard procedure:

1. In the desktop client, right-click the client and select **About**. Record the displayed client version.
2. If support needs more detail, run **Error Detection** and record both the client version number and program version number shown there.
3. Ask the administrator for the deployed server version. The client version does not prove the server version.
4. Match the confirmed server version to the dated heading in `release.md` before following version-specific navigation or feature instructions.

#### Version differences

The available user guide documents **About** and **Error Detection** for the desktop client. Server releases and their dates are listed separately in `release.md`. This distinction matters at boundaries such as 8.1.8.0 for administrator navigation, 8.1.8.6 for user two-factor authentication, and 8.1.8.7 for the redesigned peer-to-peer transfer page.

#### Important notes

Record the full displayed value rather than rounding it to “8.1.8.” Do not infer a version from a documentation filename, a screenshot, or one visible feature. If **About** is unavailable because the client cannot be opened, use the fallback in FAQ-VERSION-012.

#### Sources

- `client.md` — “3. Error detection” and “5. About Raysync”
- `release.md` — “v8.1.8.0” through “v8.1.8.7”

### FAQ-VERSION-002 | Why do administrator-provided Raysync instructions use different labels after version 8.1.8.0?

- Product: Raysync
- Audience: End user
- Applies to: Before 8.1.8.0 versus 8.1.8.0 and later
- Feature: Version-specific instruction labels
- User intent: Interpret administrator guidance without entering the admin portal
- Keywords: legacy instructions, 8.1.8.0, renamed areas, administrator guidance

#### Short answer

Version 8.1.8.0, released on 2025-03-05, reorganized administrator navigation. As an end user, you may therefore receive prerequisite instructions, support questions, or policy explanations that use either legacy labels or the newer guide-family labels. A mismatch between the words in an older article and the administrator’s current screen does not by itself mean the requested user action is unavailable.

Follow the user-facing action your administrator gives you—for example, retry login, collect a task error, or confirm a group library—while the administrator translates the server-side prerequisite for the installed version. You do not need admin-portal access to perform that translation.

#### Version differences

Legacy source files are explicitly labeled for versions before 8.1.8.0, while matching `v8180-*` files belong to the later guide family. The release entry says administrator navigation was optimized; it does not claim that every user portal label changed at the same boundary. Confirm the server version before deciding which prerequisite wording applies.

#### Important notes

Do not request elevated access merely because a help article names an administrator area. Give the administrator the article title, feature name, server version if known, and your user-visible symptom. The administrator can locate the corresponding current control. Keep user portal and admin portal roles distinct.

#### Sources

- `release.md` — “v8.1.8.0,” item 1
- `security.md` and `v8180-security.md` — front-matter menu paths
- `email-authentication.md` and `v8180-email-authentication.md` — front-matter menu paths
- `external-http.md` and `v8180-external-http.md` — front-matter menu paths
- `ldap.md` and `v8180-ldap_ad.md` — front-matter menu paths
- `oidc.md` and `v8180-oidc.md` — front-matter menu paths
- `linux-user.md` and `v8180-unix-system.md` — front-matter menu paths
- `default-permission.md` and `v8180-permission-setting.md` — front-matter menu paths
- `space.md`, `v8180-storage.md`, `v8180-group-management.md`, `v8180-file.md`, and `v8180-recycle-bin.md` — front-matter menu paths

### FAQ-VERSION-003 | What changed for end users in Raysync 8.1.8.1?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.1
- Feature: User portal transfers and language support
- User intent: Understand the 8.1.8.1 user-visible release changes
- Keywords: 8.1.8.1, pause transfer, cancel transfer, Turkish

#### Short answer

Raysync 8.1.8.1 was released on 2025-04-02. Its main documented user portal change is that users can pause or cancel web transfer tasks without the client. The same release also made Turkish localization available as an optional interface language.

#### Version differences

Before 8.1.8.1, the release history does not claim this client-free pause/cancel control. Version 8.1.8.1 changes control of an existing web task; it does not make every client-dependent feature available in the browser. The core file guide still distinguishes web transfer from client-dependent functionality such as sync creation and video preview.

#### Important notes

“Pause or cancel without client” does not mean that every client feature became available in the browser. If a high-speed or client-dependent task cannot be created, start the browser plug-in or desktop client. Also distinguish a web task shown in the lower-right transfer list from a desktop-client task.

#### Sources

- `release.md` — “v8.1.8.1,” items 1 and 3 and update date
- `files.md` — “1.4 Start the client” and “2. File Operations”
- `client.md` — “1. Transfer List”

### FAQ-VERSION-004 | Why is an 8.1.8.3 link or P2P log control missing in 8.1.8.2?

- Product: Raysync
- Audience: End user
- Applies to: Versions 8.1.8.2 and 8.1.8.3
- Feature: Link protection and P2P log details
- User intent: Decide whether a missing control requires version 8.1.8.3
- Keywords: 8.1.8.2, 8.1.8.3, logs, share-download link, connection type

#### Short answer

The control may belong to 8.1.8.3 rather than 8.1.8.2. Use 8.1.8.3 when you need the documented direct/relay connection type in a peer-to-peer transfer log or the ability to enable and disable a share-download link. Version 8.1.8.2 does not claim those controls; its relevant changes are log-list classification, virtual-path interaction, and the Linux desktop client.

Do not use recipient-email protection as a clean 8.1.8.2-versus-8.1.8.3 differential. The release history documents specified-email access in 6.8.8.2 and describes recipient-email protection again in 8.1.8.3. The supplied sources do not explain whether the later entry is a new scope, revision, or repeated description.

#### Version differences

Both 8.1.8.2 and 8.1.8.3 have the published date 2025-06-30, so the date alone cannot distinguish them. Confirm the complete version using FAQ-VERSION-001. P2P connection-type logging and shared-link enable/disable have clear 8.1.8.3 entries; recipient-email protection retains the duplicate-release uncertainty described above.

#### Important notes

The P2P connection type is an administrator log detail; an end user can still inspect failure reasons in desktop-client task details. For a recipient-email-protected link, use the specified email identity, but do not infer its minimum version from the duplicated release entries. If 8.1.8.2 lacks shared-link enable/disable, do not troubleshoot that specific absence as a browser fault.

#### Sources

- `release.md` — “v6.8.8.2,” items 2–3, and “v8.1.8.2” and “v8.1.8.3”
- `v8180-log.md` — P2P direct/relay connection type
- `share-link.md` — “Enable/Disable Shared Link Functionality”
- `invitation-link.md` — “Support specify the recipient's email to protect shared content”
- `files.md` — “Desktop Client: Linux Version Now Available”

### FAQ-VERSION-005 | What changed with malicious-IP protection in Raysync 8.1.8.4?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.4 and later
- Feature: Malicious-IP login restrictions
- User intent: Understand a new login security block
- Keywords: 8.1.8.4, malicious IP, blacklist, login restriction

#### Short answer

Raysync 8.1.8.4 was released on 2025-06-30 and introduced a malicious-IP login restriction policy. It also added an email alert to administrators for malicious-IP blacklist events.

For an end user, the practical change is that a login may be denied because the current IP is subject to this policy. Stop repeated attempts and ask the administrator to review the event; the release notes do not document a self-service unblock. For the end-user response procedure, see FAQ-SECURITY-010.

#### Version differences

Earlier versions already supported ordinary IP allowlists and blocklists. Version 8.1.8.4 is the first release entry that names the malicious-IP login restriction policy and the related administrator email alert. Do not assign this specific policy to 8.1.8.3 or infer it merely from the presence of a normal IP blacklist.

#### Important notes

Do not switch networks to evade a block. Provide the login time, account, and displayed message to the administrator. The available sources do not state the malicious-detection thresholds, so they should not be guessed.

#### Sources

- `release.md` — “v8.1.8.4,” items 1–2 and update date
- `v8180-security.md` — “2. Access Restrictions” and “4. Login Settings”
- `security.md` — “2. Access Restrictions”

### FAQ-VERSION-006 | Will Raysync 8.1.8.6 change my login verification or transfer priority?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.6 and later
- Feature: Two-factor authentication and transfer priority
- User intent: Decide whether an 8.1.8.6 change explains a new prompt or speed allocation
- Keywords: 8.1.8.6, 2FA, Authenticator App, email verification, transfer priority

#### Short answer

Raysync 8.1.8.6, released on 2026-03-19, is the documented boundary for user two-factor authentication and user transfer priority. Where the deployment supports and enables it, a user can be asked for email verification or an Authenticator App code. Administrator two-factor authentication was already introduced in 8.1.8.3; 8.1.8.6 does not introduce that administrator capability for the first time.

Transfer priority is administrator-controlled. When enabled, the server assigns low, medium, or high priority through user roles and allocates available bandwidth using priority and configured inbound/outbound server bandwidth. The documented default role priority is medium. The source also says a user’s bandwidth “will be shared with their inviter/sharer,” but it does not define the allocation direction, participants, or calculation. Do not infer a particular bandwidth split; ask the administrator how the configured deployment applies that statement.

#### Version differences

The current `v8180-security.md` guide family describes email and Authenticator App methods, but the guide family does not mean those user options existed from 8.1.8.0. Use `release.md` for availability: administrator two-factor authentication at 8.1.8.3, then user two-factor authentication and transfer priority at 8.1.8.6. The legacy guide separately documents local-user email validation.

#### Important notes

Priority is not a guaranteed fixed speed. If a login prompt or transfer behavior changed after an upgrade, ask the administrator which authentication scope and role priority are assigned to your account.

#### Sources

- `release.md` — “v8.1.8.3,” item 9, and “v8.1.8.6,” items 1–2 and update date
- `v8180-security.md` — “4. Login Settings,” “Multi-factor Authentication”
- `v8180-transfer.md` — “Transfer priority”
- `v8180-user-roles.md` — “Transfer priority”
- `security.md` — “4. Login Settings,” legacy email validation

### FAQ-VERSION-007 | Where is the peer-to-peer transfer workflow boundary around versions 8.1.8.6 and 8.1.8.7?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.6 and 8.1.8.7 and later
- Feature: P2P workflow boundary
- User intent: Understand the documented release boundary without inferring the 8.1.8.6 workflow
- Keywords: P2P, 8.1.8.6, 8.1.8.7, device ID, remote computer

#### Short answer

The clear release boundary is version 8.1.8.7. The release list, dated 2026-07-07, records a redesigned peer-to-peer transfer page, and the current workflow guide requires a client at version 8.1.8.7 or later. The quick-start source separately labels an earlier workflow for versions before 8.1.8.6.

Exactly version 8.1.8.6 is not assigned to either workflow by those labels. The evidence therefore supports three statements only: before 8.1.8.6 uses the documented earlier flow; 8.1.8.7 and later uses the redesigned flow; and exactly 8.1.8.6 is a documentation gap.

#### Version differences

`p2p-task.md` labels its flows “Version 8187+” and “Version Before 8186,” while `p2p-8186.md` is titled “Before Version 8186.” Because neither source assigns exactly 8.1.8.6, do not classify it as legacy or redesigned solely from a filename or neighboring release.

#### Important notes

If support for exactly version 8.1.8.6 is required, report the full client and server versions and ask the administrator or Raysync support which workflow that deployed build uses. This FAQ intentionally states only the release boundary and does not reproduce interface instructions.

#### Sources

- `release.md` — “v8.1.8.7,” item 3 and update date
- `p2p-task.md` — “Quick Start—Version 8187+” and “Quick Start—Version Before 8186”
- `p2p.md` — current P2P page sections
- `p2p-8186.md` — legacy send and receive sections

### FAQ-VERSION-008 | Which Raysync version added a Japanese interface?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.7 and later
- Feature: Japanese language support
- User intent: Find the release that supports Japanese
- Keywords: Japanese, language, localization, 8.1.8.7

#### Short answer

Raysync 8.1.8.7, released on 2026-07-07, added Japanese interface support for both the desktop client and user portal. In the user portal, language can be switched from the upper-right area of the login page; in the desktop client, language can be switched in Settings.

#### Version differences

The release list records Turkish localization in 8.1.8.1 and Japanese in 8.1.8.7. Earlier releases should not be assumed to include Japanese merely because the current documentation shows a general language selector.

#### Important notes

If Japanese is absent, confirm both client and server versions and report their full values to the administrator. Check the visible selector only after confirming those versions. A newer client connected to an older server, or an older client connected to a newer server, may not present the same language choices. The source does not document a separate Japanese language-pack installation for end users.

#### Sources

- `release.md` — “v8.1.8.7,” item 2 and update date; “v8.1.8.1,” item 3
- `profile.md` — “6. Select Language”
- `client.md` — “5. About Raysync”

### FAQ-VERSION-009 | Which Raysync version supports the collaboration-link control I need?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.7.8.2 and later; individual controls have later boundaries
- Feature: Collaboration links
- User intent: Match a required share-download or invite-upload control to its release
- Keywords: share-download link, invite-upload link, email, filters, desktop client

#### Short answer

Match the control to the documented boundary:

- To let an external invite-upload link user delete files in the invited location, use 6.7.8.2 or later.
- For anyone-with-link email verification or private recipients, the release history first lists the capability in 6.8.8.2. “Private recipient” is not defined in the supplied source, so do not assume how it differs from a specified email recipient.
- For user portal link filters, use 8.1.8.0 or later.
- To enable or disable an existing share-download link, use 8.1.8.3 or later.
- To upload or download through Raysync links in the desktop client, use 8.1.8.4 or later.

Specified-email or recipient-email protection does not have a clean boundary in the release history: specified-email access appears in 6.8.8.2 and recipient-email protection appears again in 8.1.8.3. The sources do not say whether 8.1.8.3 is a new scope, a revision, or a duplicate description. Confirm the option in the deployed interface.

#### Version differences

The current share-download and invite-upload guides combine controls introduced across several releases. Confirm the deployment using FAQ-VERSION-001, then use clear `release.md` entries where available. Preserve the recipient-email duplicate-release uncertainty instead of treating 8.1.8.3 as an unambiguous first introduction.

#### Important notes

> **Warning:** **Allow deletion** on an invite-upload link permits an external link user to delete files in the invited upload location. It does not mean deleting the invitation link itself. Enable this destructive permission only for the intended workflow and recipients.

Link visitors cannot override scope, password, expiration, email identity, or download settings. Disabled, canceled, expired, or email-restricted access must be resolved by the creator or administrator.

#### Sources

- `release.md` — “v6.7.8.2,” “v6.8.8.2,” “v8.1.8.0,” “v8.1.8.3,” and “v8.1.8.4”
- `share-link.md` — creation, access, management, and enable/disable sections
- `invitation-link.md` — “1.3” option “Allow deletion,” plus access and management sections
- `files.md` — “File Upload and Download through Raysync Links Supported”

### FAQ-VERSION-010 | Why did my Raysync login or certificate behavior change after an upgrade?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; key boundaries at 8.1.8.3, 8.1.8.4, and 8.1.8.6
- Feature: Security release differences
- User intent: Match a changed security experience to the correct release boundary
- Keywords: security versions, TLS, 2FA, malicious IP, client certificate

#### Short answer

First identify the changed experience. Administrator two-factor authentication is documented from 8.1.8.3. Malicious-IP login restrictions begin at 8.1.8.4. User two-factor authentication, including the documented Authenticator App option where supported and enabled, begins at 8.1.8.6. Do not describe 8.1.8.6 as introducing administrator two-factor authentication anew.

For certificate behavior, the 8.1.8.0 and later guide explicitly says the built-in certificate is for transfer encryption only and HTTPS web-session encryption needs an administrator-provided certificate. The legacy guide uses broader wording for encrypted web access and file-transfer encryption.

#### Version differences

The legacy **Login Settings** guide documents local-user email validation. The current `v8180-security.md` guide family describes a broader multi-factor interface, but its `v8180` name identifies the navigation family, not the release in which every later option became available. Use the release boundaries above when deciding whether a prompt should exist.

#### Important notes

Do not assume a current guide’s option exists in an older deployment. For a malicious-IP block, follow FAQ-SECURITY-010. For a certificate warning or missing verification code, preserve the exact message and contact the administrator rather than bypassing the control.

#### Sources

- `release.md` — “V6.5.8.0,” “v8.1.8.3,” “v8.1.8.4,” and “v8.1.8.6”
- `security.md` — legacy Antivirus, Access Restrictions, Login Settings, Certificate Management, and Sensitive Words sections
- `v8180-security.md` — current corresponding sections
- `certificate.md` — “TLS Certificate”

### FAQ-VERSION-011 | Which Raysync 8.1.8.x release supports the transfer control I need?

- Product: Raysync
- Audience: End user
- Applies to: Versions 8.1.8.1 through 8.1.8.7
- Feature: Client and web task behavior
- User intent: Match a transfer control to its minimum documented release
- Keywords: web tasks, client tasks, filtering, multi-channel, sync

#### Short answer

Choose the minimum documented release for the control:

- Pause or cancel a web transfer task without the client: 8.1.8.1.
- Use the Linux desktop client: 8.1.8.2.
- Use documented real-time sync updates: 8.1.8.3.
- Upload or download through Raysync links in the desktop client: 8.1.8.4.
- Use multi-channel transfer, client task sorting, or creation-time filtering: 8.1.8.6.
- Filter client tasks by task name or task status, or use the documented desktop-client sync improvement: 8.1.8.7.

#### Version differences

Creation-time filtering and task sorting belong to 8.1.8.6; task-name and task-status filtering belong to 8.1.8.7. Do not assign all filters to the newest release. The client task list still separates general transfer tasks, sync tasks, and peer-to-peer transfer tasks, and web fallback remains narrower than client operation.

#### Important notes

Confirm the deployed version with FAQ-VERSION-001 before treating a missing control as a client fault. Multi-channel transfer requires administrator network preparation, while real-time sync is documented for upload and local storage only. Destructive sync processing options are covered in FAQ-TROUBLE-015.

#### Sources

- `release.md` — “v8.1.8.1” through “v8.1.8.7” and their update dates
- `client.md` — “1. Transfer List” and “2. Transfer Settings”
- `files.md` — client startup, sync, real-time sync, and link transfer sections
- `v8180-transfer.md` — client app, transfer, sync, and peer-to-peer sections

### FAQ-VERSION-012 | How do I identify the Raysync version when the client or About screen is unavailable?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Version-aware support
- User intent: Collect fallback version evidence for support
- Keywords: unavailable client, About unavailable, unknown version, server version, support information

#### Short answer

If the client is unavailable or its **About** screen cannot be opened, do not infer the version from the interface. If **Error Detection** can still run, save its report and record the client version and program version values it displays. If it cannot run, record the user portal address, exact error or detection message, operating system, browser, and visible control names.

Send that evidence to the administrator and ask for the deployed server version. A client value, when available, does not prove the server version. If the client later opens and **About** becomes available, use the canonical procedure in FAQ-VERSION-001 rather than repeating it here.

#### Version differences

Visible controls and screenshots can help support route the case, but they cannot establish the release by themselves. Current topic pages may contain edits made after the installed build. The administrator’s server record, any available Error Detection values, and the dated entries in `release.md` are the relevant fallback evidence.

#### Important notes

Do not reinstall the client or change server, certificate, firewall, storage, or permission settings merely to identify the release. If organizational policy permits a screenshot, remove account names, private addresses, paths, and other sensitive details. Never include passwords or verification codes. If no version value is available, say so explicitly instead of assigning the deployment to a legacy or current guide family.

#### Sources

- `client.md` — “3. Error detection” and “5. About Raysync”
- `release.md` — “v8.1.8.0” through “v8.1.8.7”
