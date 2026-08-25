### FAQ-TROUBLE-001 | Why does the user portal say the Raysync client is not detected?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions using the browser plug-in
- Feature: Client detection
- User intent: Restore high-speed portal transfers
- Keywords: client not detected, browser plug-in, web transfer, raysync-watch

#### Short answer

The portal has not connected to the browser plug-in client. Without an active client, Raysync can switch to web TCP mode, which supports normal upload, normal download, invite upload, and share download, but client-dependent features are unavailable.

#### Likely cause

The user portal cannot detect an active browser plug-in connection. Raysync documents an automatic switch to web TCP mode when the browser plug-in is not activated. This is a detection state, not by itself a diagnosis of installation or startup failure.

#### What the user can check

Confirm whether the automatic web TCP fallback appears and whether normal upload, normal download, invite upload, or share download remains available. Record the exact detection message, browser and operating system, whether the client icon appears, and whether the state changes after the normal client-start attempt described in the user guide. Detailed failure after that attempt belongs in FAQ-TROUBLE-002.

#### When to contact an administrator

Contact the administrator if detection does not recover after the normal start attempt, or if the portal neither detects the client nor provides the documented web fallback. Provide the recorded message, browser, operating system, client version if known, and whether web TCP transfer works.

#### Version differences

Version 8.1.8.1 added the ability to pause or cancel web transfer tasks without the client; it did not remove the client requirement for client-dependent functions.

#### Important notes

Use only the client package and portal address approved by your organization.

#### Sources

- `files.md` — “1.4 Start the client”
- `configuration.md` — “1.2 Client settings,” “Configure URL”
- `profile.md` — “2. Browser Usage Tips”
- `release.md` — “v8.1.8.1,” item 1

### FAQ-TROUBLE-002 | Why does the Raysync client still fail after a normal start attempt?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Client startup
- User intent: Diagnose repeated startup failure after the documented attempt
- Keywords: client not started, Start button, desktop client, browser plug-in

#### Short answer

This FAQ applies after you already used the normal **Transfer List > Start** attempt. If the browser plug-in or desktop client still does not run or reconnect, record what happened and collect client evidence rather than repeating the complete installation or launch procedure.

#### Likely cause

The browser protocol/application prompt may have been dismissed, the client application may have exited, or startup may be failing repeatedly. If the client opens but does not connect, its server address or connectivity may also need administrator review. Detection state and automatic web fallback are covered in FAQ-TROUBLE-001.

#### What the user can check

Note whether the browser displayed the request to open `raysync-watch.exe`, whether it was approved, whether the client opened and then exited, and whether the failure repeats. If the client can open, run **Error Detection** and save its report; it includes version, port connectivity, configuration, and server information. Confirm the server address only against the value supplied by the administrator.

#### When to contact an administrator

Contact the administrator when the protocol prompt never appears after the normal attempt, the application immediately exits, startup repeatedly fails, or Error Detection reports a connectivity problem. Provide the timeline, prompt result, server address used, and error-detection report. This FAQ does not repeat the installation or first-launch procedure.

#### Version differences

The same startup workflow is documented across the current user guide. The release list records a Linux desktop client in 8.1.8.2.

#### Important notes

Do not reinstall repeatedly or change the launch URL, firewall, or server address without administrator guidance. Those changes can obscure the original startup failure.

#### Sources

- `files.md` — “1.2 Desktop Client: Linux Version Now Available,” “1.4 Start the client”
- `client.md` — “2.4 Advanced Settings,” “Automatically run at start up,” and “6. Exit”
- `release.md` — “v8.1.8.2,” item 3

### FAQ-TROUBLE-003 | Why can’t I log in to the Raysync user portal?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: User login
- User intent: Diagnose a rejected login
- Keywords: login failed, incorrect password, account locked, IP restriction

#### Short answer

Use the exact portal address, account name, password, and authentication method assigned to you. A first login may require a password change. A failure can also result from an incorrect password, an account lockout or inactivity disablement, or an IP access restriction.

#### Likely cause

The user guide explicitly shows an “incorrect username or password” result. Security settings can lock an account after consecutive failures, disable it after configured inactivity, or restrict login by IP. LDAP/AD users may need the directory account format configured by the organization.

#### What the user can check

Confirm the portal URL and selected authentication method, enter the assigned account name carefully, and complete any first-login password reset. Stop repeated guesses if credentials are uncertain. If an approved **Forget Password** option is present, use it with your login email.

#### When to contact an administrator

Contact the administrator if the account may be locked or inactive, the login method is unclear, the network is restricted, or password recovery is unavailable.

#### Version differences

The legacy guide documents username/password login, first-login password reset, and local-user email validation. User two-factor authentication is documented from version 8.1.8.6 where supported and enabled. The account format, default authentication method, and required verification remain deployment-specific administrator prerequisites.

#### Important notes

Do not share passwords or verification codes.

#### Sources

- `profile.md` — “1. User login” and “4.4 Forget Password”
- `security.md` — “2. Access Restrictions” and “4. Login Settings”
- `v8180-security.md` — “2. Access Restrictions” and “4. Login Settings”
- `release.md` — “v8.1.8.6,” item 2

### FAQ-TROUBLE-004 | Why didn’t I receive the Raysync login verification email?

- Product: Raysync
- Audience: End user
- Applies to: Legacy local-user email validation and user multi-factor authentication from 8.1.8.6 where supported
- Feature: Email verification delivery
- User intent: Complete two-factor login
- Keywords: verification email missing, email code, 2FA, system mailbox

#### Short answer

Email verification depends on the Raysync system mailbox configured by the administrator and on the login email stored for your account. A missing message cannot be repaired from the login page if the server mail service or account email is wrong.

#### Likely cause

The system mailbox may not be configured or available, or your account may not have the expected login email. The security guides make system-mail configuration a prerequisite for email verification.

#### What the user can check

Confirm that you are checking the login email associated with the Raysync account. Check the mailbox’s spam or organizational quarantine according to your normal email procedures, and avoid repeatedly requesting codes if the page does not document that action.

#### When to contact an administrator

Contact the administrator if no message arrives. Ask them to verify your account email and the configured system mailbox; administrators can test the mail settings. Provide the login time and account name, not your password.

#### Version differences

Legacy email validation is documented separately for local users. The current `v8180-security.md` guide family describes email verification for user login and user-information changes with IP-based scopes, but the `v8180` guide family is a navigation family rather than an availability claim from 8.1.8.0. The release list introduces administrator two-factor authentication in 8.1.8.3 and places user two-factor authentication at 8.1.8.6. The later user email-verification behavior therefore applies from 8.1.8.6 where supported and enabled.

#### Important notes

Never send a received verification code to another person.

#### Sources

- `security.md` — “4. Login Settings,” “Email validate”
- `v8180-security.md` — “4. Login Settings,” “Multi-factor Authentication”
- `configuration.md` — “1.1 Email settings”
- `profile.md` — “4.1 User Message”
- `release.md` — “v8.1.8.3,” item 9, and “v8.1.8.6,” item 2

### FAQ-TROUBLE-005 | Why is the Forget Password option unavailable or not working?

- Product: Raysync
- Audience: End user
- Applies to: User portal deployments with password recovery enabled
- Feature: Forgot password
- User intent: Reset a forgotten password
- Keywords: forget password, reset password, login email, system mail

#### Short answer

This FAQ covers only failed or unavailable recovery. If **Forget Password** is absent, does not send a message, rejects a delivered code as expired, or fails before a new password can be submitted, record that symptom and escalate it. The normal recovery sequence and current-form password guidance are covered in FAQ-START-005.

#### Likely cause

The documented prerequisites are a configured system mailbox and the user’s login email. The account email may be missing or wrong, the system email service may be unavailable, or a delivered code may have passed its documented 10-minute validity period. The supplied sources do not specify other reasons why **Forget Password** might be absent.

#### What the user can check

Distinguish the failure stage: option absent, message not delivered, code expired or rejected, or submission failed. Record the time, account name, login email domain, and exact message. Do not include the code or a proposed password in the evidence.

#### When to contact an administrator

Contact the administrator for any of those failed stages. Ask them to verify the system mailbox and the login email stored for your account. If mail arrived but the page still failed, provide the timing and exact error without disclosing the verification code.

#### Version differences

Password retrieval was added in version 6.2.8.0; later guides continue to document the user portal flow.

#### Important notes

Do not repeatedly request codes while collecting evidence, and never disclose a recovery code. Follow FAQ-START-005 only after the recovery function is available and delivering a current code.

#### Sources

- `profile.md` — “4.4 Forget Password”
- `configuration.md` — “1.1 Email settings”
- `release.md` — “v6.2.8.0,” item 11

### FAQ-TROUBLE-006 | Why does my general transfer task appear stuck or not progress?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: General transfer tasks
- User intent: Inspect a non-progressing task
- Keywords: transfer stuck, paused, task details, progress, retry

#### Short answer

Open the desktop client task list and inspect the general transfer task and its file details. Raysync shows progress, speed, file status, transfer count, and an error reason. A general transfer task may be paused, waiting for the configured unchanged-file check, or unable to progress because of connectivity, permission, or server errors.

#### Likely cause

Documented causes include a paused task, a pre-transfer check waiting for the file to remain unchanged for the configured interval, or a reported transfer error. Error Detection can expose failed port connectivity and produce a diagnostic report.

#### What the user can check

Confirm the client is running. Open **Transfer List**, double-click the general transfer task, and inspect its file status, error reason, speed, transmission mode, delay, and packet loss. Start or retry only where the client offers that action. Run **Error Detection** if the task still does not progress.

#### When to contact an administrator

Contact the administrator if port checks fail, the task reports a server or permission error, or retries fail. Provide the task name, time, status, and client error-detection report.

#### Version differences

Version 8.1.8.7 added task-name/status filtering and more detailed failure information in operation logs; client task details already exposed file error reasons.

#### Important notes

Do not delete a task until its details needed for diagnosis are recorded.

#### Sources

- `client.md` — “1. Transfer List,” “1.1 General transfer tasks,” “2.4 Advanced Settings,” “Check before transfer start,” and “3. Error detection”
- `release.md` — “v8.1.8.7,” items 4 and 7

### FAQ-TROUBLE-007 | Why is my Raysync server transfer limited to about 5 Mbps?

- Product: Raysync
- Audience: End user
- Applies to: Unactivated Raysync servers
- Feature: License activation bandwidth
- User intent: Explain the unactivated-server limit
- Keywords: 5 Mbps, license, unactivated server, speed limit

#### Short answer

An unactivated Raysync server has a documented default bandwidth of 5 Mbps. License activation is required to experience the maximum speed.

#### Likely cause

The server license has not been activated or activation has not taken effect. This is a server-wide condition, not a per-task desktop client setting.

#### What the user can check

Compare the observed rate across more than one task and ask whether the deployment is activated. You can also inspect the client task speed and details, but an end user cannot activate the server.

#### When to contact an administrator

Contact the administrator if transfers consistently approach the documented 5 Mbps ceiling. Ask them to verify license status. License activation and the required server restart are administrator operations.

#### Version differences

The current server information guide documents the 5 Mbps default. The release list does not identify a later removal of this unactivated-server behavior.

#### Important notes

Do not confuse 5 Mbps (megabits per second) with file-size units shown elsewhere. Other bandwidth limits and network conditions can also reduce speed, so the 5 Mbps observation alone does not prove license state.

#### Sources

- `server-info.md` — “1. Server Settings,” license activation note
- `license.md` — “Online Activation” and “Offline Activation”
- `client.md` — “1. Transfer List”

### FAQ-TROUBLE-008 | Why is my Raysync transfer slower than expected?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Transfer performance
- User intent: Check documented speed controls
- Keywords: slow transfer, bandwidth limit, UDP speed, packet size

#### Short answer

Speed can be limited by client maximum-speed settings, administrator global or time-period limits, group/user limits, server bandwidth, network quality, or the unactivated-server 5 Mbps default. Start with bandwidth settings, task evidence, and **Error Detection** rather than firewall port lists.

#### Likely cause

The client may have a per-task upload/download maximum, the server may enforce a global or time-period limit, a user or group policy may impose another ceiling, or UDP performance may be poor. The client task detail view provides average speed, delay, packet loss, packet size, transmission mode, and file-level errors. An unactivated server is separately documented with a default bandwidth of 5 Mbps.

#### What the user can check

Review **Settings > Bandwidth** for maximum upload/download values. Open the affected task and record its transmission mode, average speed, delay, packet loss, and file-level error reason. Run **Error Detection** and its UDP speed test when UDP transfer is slow. Do not raise minimum speed blindly; the guide relates it to actual client and server bandwidth.

#### When to contact an administrator

Contact the administrator when the evidence indicates a failed connectivity check, a server/user/group limit, or the unactivated 5 Mbps cap. Provide the error-detection report and task details. If a specific port fails or multi-channel transfer is involved, use FAQ-TROUBLE-009 for version-matched firewall escalation.

#### Version differences

Version 8.1.8.6 added multi-channel transfer, long-queue improvements, and GSO. These release improvements do not override a configured bandwidth limit or a poor UDP test result.

#### Important notes

Performance settings are not guaranteed speeds. Change one user-controlled setting at a time and preserve task evidence before escalation.

#### Sources

- `client.md` — “2.1 Transfer,” “2.2 Bandwidth,” and “3. Error detection”
- `configuration.md` — “2.1 Transfer settings”
- `server-info.md` — license and bandwidth descriptions
- `release.md` — “v8.1.8.6,” items 8–10

### FAQ-TROUBLE-009 | What should I do when Raysync reports a port or connectivity failure?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Port connectivity
- User intent: Collect evidence for a network failure
- Keywords: port failure, firewall, Error Detection, UDP, TCP

#### Short answer

Run the desktop client’s **Error Detection** and record the failed service port. For the current firewall guide, the documented minimum HTTP set is TCP 8090, 9090, 2480, and 2442 plus UDP 32001; the minimum HTTPS set is TCP 8091, 9091, 2481, and 2443 plus UDP 32001. Peer-to-peer transfer is consistently documented as TCP 3443, UDP 3478, and UDP 32003.

#### Likely cause

A required server firewall, cloud security-group, or NAT mapping may be missing. Optional multi-channel port values conflict between `client.md` and `firewall.md`; `configuration.md` does not provide a third multi-channel list. Because those sources disagree, this FAQ does not select or reproduce a competing matrix.

#### What the user can check

Confirm that you are using the approved server address and network. Run **Error Detection**, including UDP speed detection if UDP transfer is slow, and save its report. Do not probe or change corporate firewall rules yourself.

#### When to contact an administrator

Contact the administrator whenever a required port check fails. Provide the failed protocol/port, time, server address, and report so they can verify firewall, NAT, and cloud rules. For multi-channel transfer, the administrator must use the deployment/firewall documentation packaged or published for the installed server build and ask Raysync support if that build-specific documentation remains inconsistent.

#### Version differences

Version 8.1.8.7 consolidated WebSocket, HTTP download, and preview ports. Always use the firewall document matching the installed server rather than an older memorized list.

#### Important notes

Opening unnecessary ports increases exposure. End users should not choose between conflicting multi-channel sources or request that every value be opened; administrators should apply only the installed-build deployment rules.

#### Sources

- `client.md` — “2.1 Transfer,” multi-channel transfer, and “3. Error detection”
- `firewall.md` — “On premise deployment” and “Cloud deployment”
- `configuration.md` — “2.3 Peer-to-Peer transfer”
- `server-info.md` — “UDP Acceleration Port”
- `release.md` — “v8.1.8.7,” item 8

### FAQ-TROUBLE-010 | Why does a peer-to-peer transfer show a relay connection instead of direct?

- Product: Raysync
- Audience: End user
- Applies to: P2P deployments; connection type visible from 8.1.8.3 logs
- Feature: P2P relay
- User intent: Understand a relayed P2P path
- Keywords: P2P relay, direct connection, transit traffic, STUN

#### Short answer

Raysync supports direct and relay connection types in P2P transfer logs. Based on the P2P and firewall documentation, a relay result means the direct path was not used and server forwarding/transit was involved. Raysync states that P2P data is not uploaded to server disk; the server carries transit traffic.

#### Likely cause

The two devices could not establish the preferred direct connection under their current networks. STUN is optional but is documented as improving the success rate of direct connections; P2P also depends on its configured service and ports.

#### What the user can check

Confirm both clients are online, P2P is enabled, and normal network connectivity exists. Reconnect the device. Do not change STUN or firewall settings yourself.

#### When to contact an administrator

Contact the administrator if relay is unexpected or materially affects performance. Provide the task and connection type so they can check P2P, STUN, and forwarding configuration.

#### Version differences

Version 8.1.8.3 added P2P connection type to transfer logs.

#### Important notes

The explanation of relay as server transit is an inference from the documented direct/relay log types, P2P transit statement, and forwarding port.

#### Sources

- `release.md` — “v8.1.8.3,” item 1
- `p2p.md` — introduction and “Core Process”
- `p2p-task.md` — “Prerequisites,” P2P and STUN services
- `firewall.md` — P2P forwarding, STUN, and transfer ports

### FAQ-TROUBLE-011 | Why does my peer-to-peer transfer fail to connect or complete?

- Product: Raysync
- Audience: End user
- Applies to: All documented P2P versions
- Feature: P2P failure
- User intent: Check P2P prerequisites
- Keywords: P2P failed, device ID, offline, network, permission

#### Short answer

P2P requires both sender and receiver to be logged in, running the client, online, and enabled for P2P. The receiver must allow incoming files, and the sender needs the current device ID or email.

#### Likely cause

One client is offline or exited, P2P is disabled, the device ID was refreshed and the old value no longer works, receiver permissions block the action, storage is insufficient, or the P2P service/ports are not configured.

#### What the user can check

Verify both clients are running and connected, both devices show P2P enabled, the receiver allows files, and the latest device ID is used. Reconnect after permission changes because the new permissions take effect on reconnection. Inspect failure details in the desktop client.

#### When to contact an administrator

Contact the administrator if the P2P switch cannot be enabled after login/network checks, or if service, STUN, or ports appear unavailable. Provide the task failure detail.

#### Version differences

For 8.1.8.7 and later, use the redesigned workflow with **Enable P2P**, **My Device ID**, **My Computer**, **Remote Computer**, and **Transfer Center**. For versions before 8.1.8.6, `p2p-task.md` documents the earlier **Send/Receive** workflow. Exactly version 8.1.8.6 is a documentation gap: the source labels “8187+” and “Before 8186” do not assign it unambiguously. Match the visible interface and ask the administrator or Raysync support if neither workflow matches.

#### Important notes

Do not expose device IDs to unauthorized people. Do not classify exactly 8.1.8.6 as legacy solely from a source filename.

#### Sources

- `p2p.md` — “Enable Peer to Peer transfer,” “View, Refresh, and Copy Device ID,” and “P2P Permission Configuration”
- `p2p-task.md` — “Prerequisites” and “Before You Start”
- `client.md` — “1.3 Peer to peer tasks”
- `release.md` — “v8.1.8.7,” item 3

### FAQ-TROUBLE-012 | Why can’t another device send files to my computer?

- Product: Raysync
- Audience: End user
- Applies to: All documented P2P versions
- Feature: P2P receiving
- User intent: Enable authorized incoming P2P files
- Keywords: cannot receive, allow receive files, P2P, save path

#### Short answer

Your client must be online with P2P enabled and **Allow receive files from others** turned on. The receiving computer also needs sufficient storage and a valid receive save path.

#### Likely cause

Receiving was turned off in P2P settings, the client or P2P feature is offline, the sender has an old device ID, the receiving path lacks capacity, or permission changes have not taken effect because the devices have not reconnected.

#### What the user can check

Open P2P settings, enable receiving, confirm the save path, copy the current device ID to the sender, and reconnect the devices. Keep only the permissions required; receiving files does not require exposing the file list.

#### When to contact an administrator

Contact the administrator if P2P cannot be enabled, the client cannot connect, or the server-side P2P service or ports are unavailable.

#### Version differences

For 8.1.8.7 and later, the redesigned page uses **Allow receive files from others**. For versions before 8.1.8.6, the documented **Receive** flow uses **Allow to receive files**. Exactly version 8.1.8.6 is not unambiguously covered because `p2p-task.md` labels its workflows “8187+” and “Before 8186.” On 8.1.8.6, match the control visible in your interface and contact the administrator or Raysync support if the instructions do not match.

#### Important notes

Do not set the receive path to system directories or important data folders. Do not assume exactly 8.1.8.6 uses the pre-8.1.8.6 workflow.

#### Sources

- `p2p.md` — “P2P Permission Configuration” and “Send Files to remote device”
- `p2p-task.md` — “Quick Start—Version 8187+” and “Quick Start—Version Before 8186”
- `client.md` — “2.3 Peer-to-Peer”

### FAQ-TROUBLE-013 | Why is upload or download unavailable in the user portal?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Upload and download availability
- User intent: Identify client, transfer-mode, or permission restrictions
- Keywords: upload unavailable, download unavailable, web transfer, client transfer

#### Short answer

Availability can depend on your permission, the administrator’s transfer-type setting, and whether the client is running. Raysync can be configured for client-only transfer, web-only transfer, or both. Without the client, web TCP mode supports normal upload/download and link transfers but not every client-dependent feature.

#### Likely cause

Your role lacks upload or download permission, the target path is forbidden or outside the allowed path, the server allows only the other transfer type, or the browser plug-in client is not active.

#### What the user can check

Confirm the intended file area and target path. Start the browser plug-in through **Transfer List > Start** if the action is client-based. Check whether the button is missing versus an attempted task showing a specific error.

#### When to contact an administrator

Contact the administrator if the button remains unavailable or permission is denied. Provide the space/group, path, action, and whether web or client transfer was attempted.

#### Version differences

Version 8.1.8.1 added web task pause/cancel without the client, not universal client-free feature parity.

#### Important notes

Do not use a different account to bypass permissions.

#### Sources

- `files.md` — “1.4 Start the client,” “2.1 Upload file,” and “2.2 Download file”
- `configuration.md` — “2.1 Transfer settings,” “Transfer type”
- `space.md` — “4.2 Space member permissions and transfer configuration”
- `release.md` — “v8.1.8.1,” item 1

### FAQ-TROUBLE-014 | Why do I get Permission denied for a file or folder action?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: File permissions
- User intent: Identify an access-policy denial
- Keywords: permission denied, forbidden path, allowed path, group permissions

#### Short answer

“Permission denied” usually identifies policy ownership rather than a missing file. The denied action may be excluded from your personal or group role, the path may be forbidden or outside allowed paths, or an externally authenticated account may receive permissions from Raysync or from the external authentication service.

#### Likely cause

Your assigned role may not allow the requested operation. A forbidden path is hidden and blocks operations in that location; an allowed-path rule limits activity to the configured files or folders. Group members can have different policy. For external HTTP authentication, the source explicitly supports either Raysync-controlled permissions or externally controlled permissions.

#### What the user can check

Record the authentication method, exact space, personal or group area, path, item name, and requested operation. Distinguish an absent path from a visible item with a disabled action and from a task that starts but returns an error. Note whether the same action works in another authorized location; do not use another account or attempt to bypass the rule.

#### When to contact an administrator

Contact the group or Raysync administrator with that evidence. If you use external authentication, ask whether Raysync or the external service owns your permissions. The correct owner must change the role or path policy; an end user cannot repair it by restarting the client.

#### Version differences

Legacy documentation assigns permissions per space/member. The 8.1.8.0 and later guide family uses user and group roles. External HTTP authentication documents both permission-ownership models in legacy and current guide families.

#### Important notes

Permission denial is not evidence that the file was deleted. Preserve the denial before asking for broader access, and request only the operation and path required for the work.

#### Sources

- `files.md` — “2. File Operations”
- `space.md` — “4.2 Space member permissions and transfer configuration” and “5. Group Folder”
- `v8180-user-roles.md` — “Permission setting description,” permissions and path rules
- `external-http.md` — “External Http Authentication,” permission ownership modes
- `v8180-external-http.md` — “External Http Authentication,” permission ownership modes
- `default-permission.md` — “Default authentication permission configuration”
- `v8180-permission-setting.md` — “Permission Setting”

### FAQ-TROUBLE-015 | Why is my sync task not running?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions with sync enabled
- Feature: Sync tasks
- User intent: Distinguish waiting from failure
- Keywords: sync not running, Idle, Schedule, sync permission, desktop client

#### Short answer

A sync task can be waiting normally for its next interval or scheduled time. The client labels these states **Idle**, **Schedule**, or **Idle (completion time)**. Sync also requires administrator permission, the global sync switch, and a running client.

#### Likely cause

The next scheduled time has not arrived, the client is not running, your account lacks sync permission, the global sync function is disabled, or the task configuration/path no longer permits the operation.

#### What the user can check

Open the client’s sync task list, read the status, schedule, source, and target paths, and confirm the client remains connected. Do not treat a documented waiting status as a failure.

#### When to contact an administrator

Contact the administrator if sync permission or the global switch is disabled, paths are inaccessible, or the task shows an error after its scheduled time. Provide task details and the error-detection report.

#### Version differences

Version 8.1.8.3 added real-time sync updates; that mode supports upload and local storage only. Version 8.1.8.7 improved desktop-client sync.

#### Important notes

> **Warning:** Sync processing modes can delete data. **Delete target file synchronously when source deleted** propagates a source deletion to the target. Other documented modes can automatically delete source files or move them and clear them later. Verify the source, target, and processing mode before retrying or editing the task.

Do not use a retry as a test if you do not understand the configured deletion behavior. Preserve the task details and ask the administrator before changing a shared or business-critical sync task.

#### Sources

- `client.md` — “1.2 Sync directory task”
- `files.md` — “2.4 Create sync task” and “2.8 The synchronization feature supports real-time updates”
- `configuration.md` — “2.2 Sync”
- `release.md` — “v8.1.8.3,” item 4, and “v8.1.8.7,” item 6

### FAQ-TROUBLE-016 | Why was a file skipped or renamed unexpectedly during transfer?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: File filtering and same-name handling
- User intent: Explain a skipped or renamed file
- Keywords: skipped file, renamed file, filter, same name, overwrite

#### Short answer

Raysync can skip files because of name/size filters, format allowlists or blocklists, “only download new files,” or the pre-transfer unchanged-file check. It can rename a source or target when a same-name file already exists, depending on task or client settings.

#### Likely cause

A configured regular-expression/size filter matched the file, the file extension is disallowed, the file kept changing during the 3–30-second pre-transfer check, or a same-name conflict selected **Rename file** instead of overwrite.

#### What the user can check

Open the task’s file details and error reason. Review the task’s filter, file-processing, and same-name settings without changing them mid-diagnosis. Confirm whether the destination already contained that name.

#### When to contact an administrator

Contact the administrator if the client forbids filter changes or a server/group policy controls formats. Provide the original name, resulting name, and task settings.

#### Version differences

Legacy and current user guides document these behaviors; navigation and available policy ownership can differ after 8.1.8.0.

#### Important notes

Do not delete either copy until content and timestamps are verified.

#### Sources

- `files.md` — “2.4 Create sync task,” file filters, pre-transfer check, and same-name handling
- `client.md` — “2.4 Advanced Settings”
- `configuration.md` — “2.1 Transfer settings,” “Transfer file format limit”

### FAQ-TROUBLE-017 | Why does a share-download or invite-upload link say it is expired or disabled?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions with collaboration links
- Feature: Link validity
- User intent: Regain authorized access to a link
- Keywords: link expired, link disabled, share-download link, invite-upload link

#### Short answer

The link creator can set an expiration time. A share-download link can also be disabled, after which it is no longer accessible; invite-upload links can be canceled. The link creator, not the visitor, must issue or re-enable valid access.

#### Likely cause

The configured expiration time passed, the creator disabled/canceled the link, download was turned off on a share-download link, or an access condition such as password, specified email, organization login, or first-device binding is not satisfied.

#### What the user can check

Use the exact current link and password supplied by the creator, complete the required login/email verification, and confirm you are using the authorized device if binding is enabled. Do not guess credentials.

#### When to contact an administrator

Contact the link creator first for validity and access scope. Contact an administrator if device unbinding or organization-wide link policy is involved.

#### Version differences

Version 8.1.8.0 added user portal link filters, and 8.1.8.3 added shared-link enable/disable. Recipient-email protection does not have a clean release boundary in the supplied evidence: specified-email access is documented in 6.8.8.2 and recipient-email protection appears again in 8.1.8.3. The sources do not explain whether the later entry changes scope or repeats the earlier capability, so verify the required email option in the deployed interface.

#### Important notes

Do not request a policy bypass for restricted content.

#### Sources

- `share-link.md` — “1.1 Create share link,” “1.3 Share link management,” and “1.4 Enable/Disable Shared Link Functionality”
- `invitation-link.md` — “1.3” link options and “1.5 Manage invite to upload links”
- `configuration.md` — “3. Link”
- `release.md` — “v6.8.8.2,” items 2–3; “v8.1.8.0,” item 7; and “v8.1.8.3,” items 2–3

### FAQ-TROUBLE-018 | Why was my transferred file moved to the Isolation Zone?

- Product: Raysync
- Audience: End user
- Applies to: Deployments with antivirus or sensitive-word detection enabled
- Feature: File isolation
- User intent: Respond safely to an isolated file
- Keywords: file isolated, antivirus, sensitive word, Isolation Zone

#### Short answer

Treat an isolated file as a security event. Stop retrying, renaming, repackaging, or redistributing it. This FAQ covers response, evidence, and escalation only; the comparison of antivirus and sensitive-word causes is in FAQ-SECURITY-012, with specialized detail in FAQ-SECURITY-011 and FAQ-SECURITY-014.

#### Likely cause

The file is no longer in the normal area because Raysync placed it in the Isolation Zone. Do not infer the specific trigger from the disappearance alone. Use the displayed isolation record to identify the documented reason.

#### What the user can check

If your account can view the Isolation Zone, record the file name, displayed reason or virus information, isolation time, originating task, source and target locations, and account. Preserve the exact text or an approved screenshot. Do not download, restore, or manipulate the isolated item as a troubleshooting experiment.

#### When to contact an administrator

Contact the administrator or security owner with the evidence and request authorized review. The end-user sources do not document self-service release or restoration from isolation, so do not assume that a retry or rename can clear the event.

#### Version differences

Antivirus isolation is documented in both legacy and 8.1.8.0 and later guide families. Sensitive-word detection appears in the release history from version 6.5.8.0. The response remains evidence collection and administrator escalation in the available documentation.

#### Important notes

Keep the isolated content contained until the authorized reviewer decides how it should be handled. Isolation protects users and data and is not a normal file-move state.

#### Sources

- `security.md` — “1. Antivirus” and “5. Detective Sensitive words”
- `v8180-security.md` — “1. Antivirus” and “6. Sensitive words”
- `files.md` — “2.6 Isolation zone”
- `release.md` — “V6.5.8.0,” item 1
