### FAQ-SECURITY-001 | How do I know whether my Raysync web session uses HTTPS and TLS?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; certificate wording differs at 8.1.8.0
- Feature: HTTPS and TLS
- User intent: Confirm that the user portal connection is encrypted
- Keywords: HTTPS, TLS, user portal, secure connection, 8091

#### Short answer

Use the HTTPS address supplied by your administrator. Raysync documents the user portal format as `https://<domain>:8091/`. The `https://` scheme indicates that the browser session uses HTTPS encryption. File-transfer encryption is a separate control, so an encrypted transfer does not turn an `http://` portal session into HTTPS.

#### Version differences

Before version 8.1.8.0, the legacy guide describes certificate services broadly as supporting encrypted web access and file-transfer encryption. The 8.1.8.0 and later guide explicitly separates HTTPS portal access from TCP TLS file transfer. In every documented version, certificate provisioning is an administrator prerequisite; an end user needs the approved HTTPS user portal address.

#### Important notes

Only the 8.1.8.0 and later guide explicitly states that the built-in Raysync certificate is for transfer encryption only. In that guide family, HTTPS web-session encryption requires an administrator-provided TLS certificate, normally a public-CA certificate matching the service domain. The legacy guide uses broader wording and should not be silently reinterpreted as the newer certificate model. If non-TLS connections are prohibited, the user portal cannot be opened over HTTP.

#### Sources

- `v8180-security.md` — “7.1 TLS certificates,” especially “Overview” and “Verification”
- `security.md` — “5.1 TLS certificates”
- `certificate.md` — “TLS Certificate”

### FAQ-SECURITY-002 | Why does my browser show a certificate warning for the Raysync user portal?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Browser certificate validation
- User intent: Respond safely to an HTTPS certificate warning
- Keywords: certificate warning, HTTPS, TLS, domain, browser

#### Short answer

Do not treat the warning as a normal login step. In the 8.1.8.0 and later guide, the built-in Raysync certificate is only for transfer encryption; HTTPS web-session encryption requires a certificate supplied by the administrator, typically issued by a public certificate authority and matching the service domain. The legacy guide uses broader wording for encrypted web access and file-transfer encryption and does not state that newer built-in-certificate limitation. Use the exact approved HTTPS address rather than bypassing the warning.

#### Version differences

The legacy security guide describes uploading a valid TLS certificate before prohibiting non-SSL access, but it should be read as legacy wording. The 8.1.8.0 and later guide is more explicit: the user portal format is `https://<domain>:8091/`, the administrator certificate should match that domain, and the built-in certificate is scoped to transfer encryption.

#### Important notes

A browser warning is not fixed by enabling encrypted file transfer in the desktop client. Web HTTPS identity and transfer encryption are distinct. If the exact approved address still warns, stop before entering credentials and ask the administrator to verify the portal certificate and server address. The source documentation does not provide an end-user certificate-repair procedure.

#### Sources

- `v8180-security.md` — “7.1 TLS certificates,” especially “Overview” and “Set External Domain / Public IP as Server Address”
- `certificate.md` — “TLS Certificate”
- `security.md` — “5.1 TLS certificates”

### FAQ-SECURITY-003 | Does Raysync encrypt files while they are being transferred?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Encrypted transfer
- User intent: Understand transport encryption
- Keywords: encrypted transfer, TLS, TCP 2443, file transfer, security

#### Short answer

HTTPS and file-transfer encryption protect different connections. HTTPS protects the browser session between your browser and the user portal. Encrypted transfer protects file data while a general transfer task or sync task is moving it. A browser padlock therefore does not prove that a file task used encrypted transfer, and an encrypted task does not make an `http://` user portal session secure.

When the option is available and not locked by policy, an end user can enable the documented **Priority to use encrypted transfer** client setting or **Turn on encrypted transfer** for a sync task. Administrators can also force or govern encrypted transfer through server client settings.

#### Version differences

The legacy security guide describes certificate services for encrypted web access and file-transfer encryption. The 8.1.8.0 and later guide more explicitly separates HTTPS portal access from TCP TLS file transfer and says the built-in certificate is only for transfer encryption. Version 8.1.8.6 added custom client-certificate support, but that does not determine whether a particular user task selected encrypted transfer.

#### Important notes

If your organization requires encryption, use the task/client option only as permitted and confirm the governing policy with the administrator. A forced administrator policy may prevent you from changing the option. Do not change portal certificates or network settings to control task encryption; those are separate concerns.

#### Sources

- `v8180-security.md` — “7.1 TLS certificates” and “7.2 Client certificates”
- `security.md` — “5.1 TLS certificates”
- `client.md` — “2.4 Advanced Settings,” “Priority to use encrypted transfer”
- `files.md` — “2.4 Create sync task,” “Turn on encrypted transfer”
- `configuration.md` — “1.2 Client settings,” “Enable encrypted transfer”
- `release.md` — “v8.1.8.6,” item 12

### FAQ-SECURITY-004 | Why am I asked for an email verification code when I log in?

- Product: Raysync
- Audience: End user
- Applies to: Legacy local-user email validation; user multi-factor authentication from 8.1.8.6 where supported
- Feature: Email two-factor authentication
- User intent: Complete a login that requires email verification
- Keywords: email code, 2FA, MFA, login, verification

#### Short answer

Your administrator has enabled email verification. Enter your password and the verification code delivered to the login email address. The legacy guide documents password-plus-email validation for local users. For deployments that support the later user multi-factor feature, the current guide allows email verification for user login and modification of user information, with IP-based verification scope.

#### Version differences

The legacy guide documents password-plus-email validation for local users and requires a configured system mailbox. The current guide family describes both email and Authenticator App methods, but guide-family placement does not establish when each option became available. The release list places administrator two-factor authentication at 8.1.8.3 and user two-factor authentication at 8.1.8.6. Version 8.1.8.6 therefore extends supported two-factor authentication to users; it does not introduce administrator two-factor authentication for the first time.

#### Important notes

Code delivery depends on the administrator’s system mailbox configuration. Confirm that your Raysync profile has the expected login email and check spam or quarantine folders. If no message arrives, an administrator must verify the configured mailbox and your account email; the end-user guides do not provide server-mail repair steps.

#### Sources

- `security.md` — “4. Login Settings,” “Email validate”
- `v8180-security.md` — “4. Login Settings,” “Multi-factor Authentication”
- `email-authentication.md` — “Email Authentication”
- `v8180-email-authentication.md` — “Email”
- `release.md` — “v8.1.8.3,” item 9, and “v8.1.8.6,” item 2

### FAQ-SECURITY-005 | Can I use an Authenticator App for Raysync two-factor authentication?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.6 and later
- Feature: Authenticator App
- User intent: Authenticate with a time-based code
- Keywords: Authenticator App, Google Authenticator, Microsoft Authenticator, TOTP, 2FA

#### Short answer

Yes, when your administrator enables the Authenticator App method. Raysync documents compatibility with authenticator applications such as Google Authenticator and Microsoft Authenticator for user login and modification of user information. Follow the enrollment and code prompts shown by your Raysync service.

#### Version differences

The legacy security guide documents local-user email validation but not an Authenticator App method. The current `v8180-security.md` guide family lists Authenticator App under multi-factor authentication; that guide family alone does not prove availability from 8.1.8.0. The release boundary for user two-factor authentication, including the documented user Authenticator App workflow where supported, is 8.1.8.6. Administrator two-factor authentication was already listed in 8.1.8.3.

#### Important notes

The administrator can apply verification to all IPs, skip listed IPs, or verify only listed IPs, so prompts may differ by network location. Keep control of the enrolled device. If the device is lost or replaced, do not attempt to bypass the code; request an authenticator reset from an administrator.

The same configured method can also protect changes to user information.

#### Sources

- `v8180-security.md` — “4. Login Settings,” “Multi-factor Authentication”
- `release.md` — “v8.1.8.3,” item 9, and “v8.1.8.6,” item 2

### FAQ-SECURITY-006 | What should I do if I lose or replace my Authenticator App device?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.6 and later when Authenticator App authentication is enabled
- Feature: Reset authenticator
- User intent: Regain access after losing an authenticator
- Keywords: reset authenticator, lost phone, new device, TOTP, 2FA

#### Short answer

Contact your Raysync administrator and request **Reset authenticator** for your user account. Raysync documents this administrative reset specifically for a user who loses the authenticator or changes devices. The end-user documentation does not provide a self-service bypass.

#### Version differences

Authenticator App authentication appears in the current `v8180-security.md` guide family, but that guide family does not establish availability from 8.1.8.0. The release list introduced administrator two-factor authentication in 8.1.8.3. Version 8.1.8.6 then records two-factor authentication for users and administrators; because administrator support already existed, this restates administrator coverage while establishing the user boundary. The documented user Authenticator App and reset workflow therefore applies from 8.1.8.6 where supported and enabled. The legacy guide only documents local-user email validation.

#### Important notes

An authenticator reset changes an account security control. Use your organization’s approved identity-verification process when requesting it. Do not share current authenticator codes, passwords, or recovery information with another user. After the administrator confirms the reset, follow the authentication prompts presented by your service.

#### Sources

- `v8180-users.md` — “1.9 Reset authenticator”
- `v8180-security.md` — “4. Login Settings,” “Multi-factor Authentication”
- `release.md` — “v8.1.8.3,” item 9, and “v8.1.8.6,” item 2

### FAQ-SECURITY-007 | Why is my Raysync account locked after failed login attempts?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Account lockout
- User intent: Understand and recover from login lockout
- Keywords: account locked, failed login, anti-brute-force, disabled, password

#### Short answer

The administrator may have enabled the anti-brute-force or login-error limit. The legacy guide allows an account to be locked after a configured number of consecutive incorrect passwords within a configured number of minutes; the threshold can be set from 3 to 30 attempts. The later guide also lists login-error limits and automatic disablement after a configured number of days without login.

#### Version differences

Both legacy and later guides document a configurable failed-login limit. The later guide also documents automatic account disablement after a configured period without login. Neither guide describes a self-service unlock action for an end user.

#### Important notes

Stop retrying uncertain passwords, because more failed attempts can meet the configured limit. Check that you are using the correct login method and account name. If the account remains locked or has been disabled for inactivity, contact the administrator; the source documentation does not describe an end-user unlock action.

#### Sources

- `security.md` — “4. Login Settings,” “Anti-brute force attacking”
- `v8180-security.md` — “4. Login Settings,” “Login Restrictions”

### FAQ-SECURITY-008 | Why does Raysync reject my password as weak?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Weak-password rules
- User intent: Choose an acceptable password
- Keywords: weak password, password rejected, password policy, reset password

#### Short answer

Two different controls can reject a password. First, an administrator can define a weak-password list containing specific values that users are not allowed to set. A password that matches that list is rejected even if it otherwise looks complex.

Second, the current reset or account form validates its own password requirements. The supplied guidance differs: `profile.md` describes three of four character categories, while `local-user.md` and `v8180-users.md` describe all four categories, 8–20 characters, and account-related exclusions. Follow the validation displayed on your current form and any policy provided by your administrator rather than treating one source as a universal hidden rule.

#### Version differences

Both the legacy and 8.1.8.0 and later security guides document an administrator-defined weak-password list. The sources do not document a release change that resolves the differing form guidance. The weak-password list and form validation are separate checks and can both apply.

#### Important notes

Do not keep retrying the same rejected value. Record the exact on-screen message and which form rejected it. If a password satisfies the current form but is still rejected, ask the administrator whether it matches the configured weak-password list. Do not disclose the proposed password itself.

#### Sources

- `security.md` — “4. Login Settings,” “Weak password settings”
- `v8180-security.md` — “4. Login Settings,” “Weak password settings”
- `profile.md` — “4.4 Forget Password”
- `local-user.md` — “Local User,” password requirements before version 8.1.8.0
- `v8180-users.md` — “Users,” password requirements for version 8.1.8.0 and later

### FAQ-SECURITY-009 | Why can I log in from one network but not another?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: IP access restrictions
- User intent: Understand location-dependent login denial
- Keywords: IP restriction, whitelist, blacklist, login denied, network

#### Short answer

Your current public or internal IP may be outside an allowed list or inside a blocked list. Raysync supports a whitelist, where only listed IPs may log in to the user portal, and a blacklist, where listed IPs may not log in. Later login settings can also restrict IP login, and multi-factor verification can vary by listed IP.

#### Version differences

Both legacy and later guides document IP allowlists and blocklists. The later guide additionally documents an IP-login restriction and IP-based scope for multi-factor verification. These controls remain administrator-managed prerequisites rather than end-user network settings.

#### Important notes

Try only an organization-approved network or VPN; do not attempt to evade the policy. If access should be permitted, give the administrator the time of the attempt and the network/IP information your organization allows you to share. Only an administrator can change the lists.

Email or Authenticator App verification prompts may also vary because later multi-factor policies can use IP lists.

#### Sources

- `security.md` — “2. Access Restrictions”
- `v8180-security.md` — “2. Access Restrictions” and “4. Login Settings”

### FAQ-SECURITY-010 | Why was my IP blocked as malicious when I tried to log in?

- Product: Raysync
- Audience: End user
- Applies to: 8.1.8.4 and later
- Feature: Malicious-IP login restrictions
- User intent: Respond to a malicious-IP access block
- Keywords: malicious IP, blacklist, login restriction, blocked IP, 8.1.8.4

#### Short answer

Raysync 8.1.8.4 introduced a malicious-IP login restriction policy. If the service blocks your address, stop repeated login attempts and contact the administrator. The release documentation also records an email alert to administrators when an address is added to the malicious-IP blacklist.

#### Version differences

This specific malicious-IP policy is listed as new in version 8.1.8.4, released on 2025-06-30. Earlier documentation supports ordinary IP allowlists and blocklists but does not identify the malicious-IP policy by that name.

#### Important notes

Do not change addresses or networks to work around the block. Provide the administrator with the time of the login attempt, the account used, and the displayed message. The available source documentation does not describe the detection thresholds or an end-user unblock procedure, so those details should not be guessed.

#### Sources

- `release.md` — “v8.1.8.4,” items 1 and 2
- `v8180-security.md` — “4. Login Settings,” “Login Restrictions”
- `security.md` — “2. Access Restrictions”

### FAQ-SECURITY-011 | What happens when Raysync antivirus detects an uploaded file?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions when antivirus is enabled
- Feature: Antivirus
- User intent: Understand virus scanning after upload
- Keywords: antivirus, ClamAV, infected file, upload, isolation zone

#### Short answer

When antivirus is enabled, Raysync scans uploaded files with ClamAV. A file detected as infected is moved to the Isolation Zone rather than remaining in the normal file area. This behavior depends on administrator configuration and a server restart after antivirus is enabled.

#### Version differences

The end-user outcome is the same in the legacy and 8.1.8.0 and later security guides: an infected uploaded file is moved from the normal file area to the Isolation Zone. The available documentation does not identify a different end-user response at the version 8.1.8.0 boundary.

#### Important notes

Do not repeatedly upload a file identified as infected or try to distribute it another way. Use the user portal’s Isolation Zone information if it is available to your account, and contact the administrator for handling under organizational policy. Virus-definition updates and antivirus enablement are administrator responsibilities.

The Isolation Zone view can show the detected virus type and the time the file was isolated.

#### Sources

- `security.md` — “1. Antivirus”
- `v8180-security.md` — “1. Antivirus”
- `files.md` — “2.6 Isolation zone”

### FAQ-SECURITY-012 | Why did a file disappear from my normal files and appear in the Isolation Zone?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions with scanning rules enabled
- Feature: Isolation behavior
- User intent: Understand why a transferred file was isolated
- Keywords: Isolation Zone, quarantined file, virus, sensitive word, file missing

#### Short answer

The two documented isolation causes are different:

- **Antivirus isolation:** after upload, ClamAV detects an infected file and Raysync moves it to the Isolation Zone.
- **Sensitive-word isolation:** during transfer, a configured term matches the file name or text-file content and Raysync places the file in the isolation area.

This FAQ only distinguishes the causes. For antivirus-specific behavior, see FAQ-SECURITY-011. For a sensitive-word match, see FAQ-SECURITY-014. For response, evidence collection, and escalation after any isolation event, see FAQ-TROUBLE-018.

#### Version differences

Both legacy and 8.1.8.0 and later security guide families document antivirus and sensitive-word isolation. Sensitive-word detection first appears in the release history at version 6.5.8.0. The available sources do not describe a different end-user classification rule after version 8.1.8.0.

#### Important notes

The same Isolation Zone can contain files isolated for different reasons, so the file’s absence from normal storage does not identify the cause by itself. Use the displayed isolation details and the specialized FAQ that matches the recorded reason. Do not infer that every isolated file contains a virus.

#### Sources

- `files.md` — “2.6 Isolation zone,” including “Virus view”
- `security.md` — “1. Antivirus” and “5. Detective Sensitive words”
- `v8180-security.md` — “1. Antivirus” and “6. Sensitive words”
- `release.md` — “V6.5.8.0,” item 1

### FAQ-SECURITY-013 | Why is a watermark displayed during video preview?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions when video watermarking is enabled
- Feature: Video watermark
- User intent: Understand the watermark in online preview
- Keywords: video preview, watermark, image overlay, security

#### Short answer

The administrator has enabled the video online-preview watermark. Raysync supports an uploaded watermark image and a configured display position. The watermark is therefore expected portal behavior for protected video preview, not a modification you can remove from the user portal.

#### Version differences

Video preview watermarking appears in the release history from version 5.0.7.8. Both the legacy and 8.1.8.0 and later guides document an administrator-supplied watermark image and display position. The end-user preview effect is unchanged in the available documentation.

#### Important notes

Do not interpret the watermark as evidence that the source video file itself has been altered; the source describes it specifically as online-preview watermark configuration. If placement prevents an authorized review, contact the administrator, who controls the watermark image and location.

The documented setting applies to online video preview, not to every file shown in the user portal.

#### Sources

- `security.md` — “3. Watermark Settings”
- `v8180-security.md` — “3. Watermark Settings”
- `release.md` — “v5.0.7.8,” item 2

### FAQ-SECURITY-014 | Why was my file isolated for a sensitive-word match?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.5.8.0 and later when sensitive-word detection is enabled
- Feature: Sensitive-word detection
- User intent: Understand content-policy isolation
- Keywords: sensitive words, file name, text file, isolation, transfer

#### Short answer

Raysync can inspect a file name and the content of a text file during transfer. If either contains a configured sensitive word, the system automatically places the file in the isolation area. The matching terms are configured by an administrator.

#### Version differences

The release list records sensitive-word detection in version 6.5.8.0. Both the legacy and 8.1.8.0 and later guides describe the same user-visible result: a configured match in a file name or text-file content sends the file to isolation.

#### Important notes

Do not evade the policy by renaming, encoding, or resubmitting the file. A match may concern the name or text content, so a filename-only review is insufficient. Provide the file name, transfer time, and displayed isolation information to the administrator for an authorized review.

Administrators can configure multiple sensitive terms, so the policy is not limited to a single documented example.

#### Sources

- `security.md` — “5. Detective Sensitive words”
- `v8180-security.md` — “6. Sensitive words”
- `release.md` — “V6.5.8.0,” item 1

### FAQ-SECURITY-015 | What is the Raysync client certificate, and what should I do after it changes?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; custom certificates supported from 8.1.8.6
- Feature: Client certificates
- User intent: Restore the browser plug-in connection after a certificate update
- Keywords: client certificate, browser plug-in, restart client, encrypted connection

#### Short answer

The client certificate establishes the encrypted connection between the browser and the browser plug-in client. In the 8.1.8.0 and later guide, the server includes this certificate; online services update it annually, while an offline service needs an administrator to upload a new certificate when it expires. After a new certificate is uploaded, exit the browser plug-in client and start it again from the web page.

#### Version differences

The legacy guide describes automatic retrieval from Raysync’s default storage for an online server and administrator upload for an offline server. The release list records support for custom client certificates in 8.1.8.6.

#### Important notes

Do not confuse the client certificate with the TLS certificate shown by the user portal HTTPS address. If restarting the browser plug-in client does not restore its connection, contact the administrator; certificate upload and source selection are not end-user tasks.

#### Sources

- `v8180-security.md` — “7.2 Client certificates”
- `security.md` — “5.2 Client Certificate”
- `release.md` — “v8.1.8.6,” item 12

### FAQ-SECURITY-016 | Who controls my Raysync permissions when I use external authentication?

- Product: Raysync
- Audience: End user
- Applies to: External HTTP, LDAP/AD, email, OIDC, and Unix/system authentication
- Feature: External-authentication permissions
- User intent: Understand why permissions differ after external login
- Keywords: external authentication, LDAP, OIDC, HTTP, permissions, roles

#### Short answer

It depends on the authentication mode. With external HTTP authentication, permissions can be controlled either by the external HTTP service or by Raysync. When Raysync controls them, the external user is created in Raysync and Raysync permissions apply. When the external service controls them, Raysync’s default permission settings do not take effect.

For LDAP/AD, email, OIDC, external HTTP with Raysync-controlled permissions, and system authentication, administrators can assign default permissions or roles to newly logged-in accounts. Accounts that have already logged in must be changed in the account list. LDAP/AD users log in with the account form required by the configured directory; the documentation specifically says AD users use `SamAccountName` at the user portal.

#### Version differences

Before 8.1.8.0, the feature is described as **Default Permission**. In later documentation it is **Permission Setting**, using default user and group roles. The 8.1.8.0 and later LDAP/AD guide also documents selecting a default authentication method and group filtering.

#### Important notes

Authentication proves identity; it does not guarantee access to every Raysync file or feature. If login succeeds but an action is unavailable, ask the administrator which system owns your permissions and whether your already-created account or group role needs adjustment.

#### Sources

- `external-http.md` — “External Http Authentication”
- `v8180-external-http.md` — “External Http Authentication”
- `default-permission.md` — “Default authentication permission configuration”
- `v8180-permission-setting.md` — “Permission Setting”
- `ldap.md` — “1. AD”
- `v8180-ldap_ad.md` — “Add default authentication” and “Support group filter”
- `oidc.md` — OIDC provider login sections
- `v8180-oidc.md` — OIDC provider login sections
- `linux-user.md` — “Linux User Authentication”
- `v8180-unix-system.md` — “Unix system”
