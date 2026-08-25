# Getting Started and Login

### FAQ-START-001 | What is Raysync and what is it used for?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Product overview
- User intent: Understand what Raysync does
- Keywords: large files, acceleration, migration, sync, peer-to-peer transfer

#### Short answer

Raysync is a secure, accelerated file-transfer product for moving large files, many small files, and enterprise data within an organization or with external partners. Typical uses include cross-border transfer, secure file delivery, file migration, file synchronization, file management, group collaboration, one-to-many distribution, and peer-to-peer transfer.

Raysync can transfer between a user's computer and server-configured storage. It also supports peer-to-peer transfer between client devices and sync tasks that keep directories aligned. The product documentation describes accelerated large-file performance, concurrent handling of many small files, TLS-protected transfer, and AES-256 encryption support.

#### Version differences

The core purposes above apply across the documented versions. Later 8.1.8.x releases add or refine individual capabilities, but `release.md` does not redefine Raysync's basic role.

#### Important notes

Available features depend on the server configuration, the user's permissions, and whether the desktop client or browser plug-in is running. An end user may therefore see only part of the full product capability.

#### Sources

- `introduction.md` — “About Raysync” and “Why Raysync?”
- `cloud.md` — “Create transfer task”
- `release.md` — release boundaries for 8.1.8.x

### FAQ-START-002 | How do I access the Raysync user portal?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: User portal access
- User intent: Open the login page
- Keywords: user portal, URL, server address, port 8090, browser

#### Short answer

Open the user portal address supplied by your Raysync administrator in a browser. The documented default format is `http://[server-IP]:8090`; for example, `http://192.168.1.1:8090`.

#### Steps

1. Obtain the Raysync server address from your administrator.
2. Enter the full address in your browser, including the port if one is required.
3. When the Raysync login page opens, use the authentication method assigned to your account.

#### Version differences

The default port example is documented across the current user guides. The sources do not identify a different end-user portal navigation flow at the version 8.1.8.0 boundary. A deployment can nevertheless use an administrator-provided address instead of the default example.

#### Important notes

Do not substitute the administrator portal address for the user portal address. The server may use a customized hostname, HTTPS address, or port, so the address provided by your organization takes precedence over the default example.

#### Sources

- `profile.md` — “User login”
- `create-task.md` — “Login the user portal”
- `oidc.md` — user portal URL and callback examples
- `v8180-oidc.md` — user portal URL and callback examples for version 8.1.8.0 and later

### FAQ-START-003 | How do I sign in to Raysync?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Local account login
- User intent: Sign in with a username and password
- Keywords: login, username, password, local account, user portal

#### Short answer

Open the Raysync user portal, enter the correct username and password, and select **Login**. If your organization has configured a different default authentication method, use the login option and credentials provided by your administrator.

#### Steps

1. Open the user portal, normally at the administrator-provided address or the documented default `http://[server-IP]:8090`.
2. Enter your username and password.
3. Select **Login**.
4. If Raysync requires a password change on first login, complete that change before entering the portal.

#### Version differences

Version 8.1.8.3 adds support for an administrator-selected default authentication method. This can change which sign-in method the page presents first, but the local-account action remains entering the username and password and selecting **Login**.

#### Important notes

An incorrect username or password prevents login. If the page expects LDAP/AD, OIDC, email, external HTTP, or Unix system credentials, local Raysync credentials may not be accepted.

#### Sources

- `profile.md` — “User login”
- `create-task.md` — “Login the user portal”
- `v8180-ldap_ad.md` — “Add default authentication”
- `release.md` — version 8.1.8.3 default-authentication change

### FAQ-START-004 | What happens on my first login?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: First-login password change
- User intent: Complete initial account setup
- Keywords: first login, reset password, initial password, sign in

#### Short answer

If the administrator has required a password reset for your first login, Raysync opens the password-reset page after you submit the initial username and password. Set the new password there, then use the new password to complete login. If no first-login reset was configured, Raysync proceeds with the normal login flow.

#### Steps

1. Enter the initial username and password provided to you.
2. Select **Login**.
3. If the reset page appears, enter and confirm a valid new password.
4. Return to the login form if prompted, enter your username and the new password, and select **Login**.

#### Version differences

The available sources do not document a version-specific difference in this first-login behavior.

#### Important notes

The first-login reset is conditional on administrator configuration. It is different from the **Forget Password** email-verification workflow. If the initial credentials are rejected rather than showing the reset page, the source documentation only identifies an incorrect username or password as the displayed condition; contact your administrator for account details.

#### Sources

- `profile.md` — “User login”

### FAQ-START-005 | How do I reset a forgotten password?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Forgotten-password recovery
- User intent: Set a new password by email verification
- Keywords: forgot password, verification code, reset, email, password policy

#### Short answer

Select **Forget Password** on the login page, enter the login email associated with your account, and use the emailed verification code to set a new password.

#### Steps

1. Select **Forget Password**.
2. Enter your login email and select **Next**.
3. Request and enter the verification code, then select **Next**.
4. Enter a valid new password and select **Confirm Reset**.

The password guidance conflicts across the supplied sources. `profile.md` says to use three of four character categories: uppercase letters, lowercase letters, numbers, and special characters. The account-creation guides `local-user.md` and `v8180-users.md` require all four categories, a length of 8–20 characters, no account name, and a password different from the account number. **Because the documented guidance differs, follow the validation shown on your current reset form and any password policy supplied by your administrator.**

#### Version differences

The supplied sources do not document a user-visible change to the reset sequence. Across documented versions, password recovery still depends on working system email configured by an administrator.

#### Important notes

The verification code expires after 10 minutes. **Resend** becomes available after 60 seconds. Forgotten-password recovery works only when the administrator has configured system email and the account has the correct login email.

#### Sources

- `profile.md` — “Forget Password”
- `v8180-users.md` — “Users” password requirements for version 8.1.8.0 and later
- `local-user.md` — “Local User” password requirements before version 8.1.8.0
- `v8180-notification.md` — “Email configuration” system-email prerequisite
- `configuration.md` — “Email settings” system-email prerequisite

### FAQ-START-006 | Why did I not receive a forgotten-password verification code?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Forgotten-password email verification
- User intent: Understand a missing password-reset code
- Keywords: forgotten password, password reset, verification code, email, resend, system mail

#### Short answer

Raysync can send the forgotten-password verification code only when system email is configured and your login email is registered correctly. Wait until the 60-second resend interval has passed, then select **Resend**. If no code arrives, ask your administrator to verify the account email and the Raysync email configuration.

#### Troubleshooting

- Confirm that you entered the login email associated with your Raysync account.
- Use **Resend** only after the documented 60-second interval.
- If repeated attempts produce no message, the documented prerequisite is administrator-configured system mail.

#### Version differences

The user profile guide documents the 60-second resend interval without a stated version difference. The system-email prerequisite also applies across the supplied current and legacy sources.

#### Important notes

The source documentation does not provide additional mail-delivery troubleshooting. If the code still does not arrive after **Resend**, contact your administrator to check the account email and system-email configuration.

#### Sources

- `profile.md` — “Forget Password”
- `configuration.md` — “Email settings”
- `v8180-notification.md` — “Email configuration” system-email prerequisite

### FAQ-START-007 | Which authentication methods can an end user use?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; choices depend on administrator configuration
- Feature: Authentication methods
- User intent: Identify valid sign-in options
- Keywords: local login, LDAP, AD, OIDC, email, external HTTP, Unix system

#### Short answer

Depending on administrator configuration, an end user may sign in with a local Raysync account or through LDAP/OpenLDAP, Windows Active Directory, OpenID Connect, email-based authentication, an external HTTP authentication service, or Unix/Linux system authentication. Only methods enabled for the deployment and account are available.

#### Version differences

Version 8.1.8.0 adds multiple authentication methods to the browser plug-in. Version 8.1.8.3 adds support for an administrator-selected default authentication method, so the login choice shown first can vary by deployment.

#### Important notes

Authentication method does not by itself determine file permissions. For external HTTP accounts, permissions may remain in the external service or be synchronized into and controlled by Raysync, depending on the integration mode. Unix system authentication requires the Raysync service to have been started with root or sudo authority; this is an administrator prerequisite.

#### Sources

- `ldap.md` — “LDAP/AD”
- `oidc.md` — “OpenID Connect”
- `external-http.md` — “External Http Authentication”
- `linux-user.md` — “Linux User Authentication”
- `v8180-ldap_ad.md` — “Add default authentication”
- `v8180-unix-system.md` — “Unix system”
- `release.md` — version 8.1.8.0 and version 8.1.8.3 authentication changes

### FAQ-START-008 | How do I sign in with LDAP or Active Directory?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions when LDAP/AD is configured
- Feature: LDAP/AD login
- User intent: Use a directory-service account
- Keywords: LDAP, OpenLDAP, Active Directory, AD, SamAccountName, domain login

#### Short answer

Open the Raysync user portal and use the LDAP/AD login method made available by your administrator. For a Windows Active Directory domain account, enter the user's `SamAccountName` as the username and use the domain password. OpenLDAP users use the credentials defined by the configured directory integration.

#### Version differences

Version 8.1.8.3 allows LDAP/AD to be selected as the default authentication method. Version 8.1.8.4 adds LDAP/AD group filtering, so only members of matching groups may be eligible for import and login.

#### Important notes

LDAP/AD must be configured by an administrator before you can use it. If the LDAP/AD option is absent or your directory credentials are rejected, ask whether your account or group is included in the configured directory paths and filters. Do not enter a distinguished name in place of `SamAccountName` for the documented Active Directory user portal login.

#### Sources

- `ldap.md` — “AD” and “OpenLdap”
- `v8180-ldap_ad.md` — “AD,” “OpenLdap,” “Add default authentication,” and “Support group filter”
- `release.md` — version 8.1.8.3 and version 8.1.8.4 authentication changes

### FAQ-START-009 | How do I sign in with OpenID Connect?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions when OIDC is configured
- Feature: OpenID Connect login
- User intent: Use an enterprise identity provider
- Keywords: OIDC, OpenID Connect, SSO, Okta, OneLogin, Google, Microsoft Entra ID

#### Short answer

Use the OpenID Connect sign-in option on the Raysync user portal, then authenticate on your organization's identity-provider page. After successful identity-provider authentication, the configured OIDC callback returns you to the Raysync user portal.

The documentation includes Okta, OneLogin, Google, and Microsoft Entra ID examples, but the exact button name and provider depend on your organization's setup.

#### Version differences

The supplied sources do not document a version-specific change to the end-user OIDC redirect and return flow.

#### Important notes

OIDC must be configured and tested by an administrator, and your identity-provider account must be assigned to the application. The authentication token exchange occurs between Raysync and the identity provider and is not exposed through the browser.

#### Sources

- `oidc.md` — “OpenID Connect” and provider login sections
- `v8180-oidc.md` — provider login sections for version 8.1.8.0 and later

### FAQ-START-010 | How do I use email authentication or sign in with an external HTTP account?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions when the selected integration is configured
- Feature: Email and external HTTP authentication
- User intent: Determine how email authentication works and use an external HTTP account
- Keywords: email authentication, external HTTP, third-party account, login

#### Short answer

For email authentication, use the email-related login method shown by your organization; the available sources do not document a separate end-user sequence or credential format. For external HTTP, use the external service credentials on the Raysync login page only when your administrator confirms that the integration is configured for Raysync-controlled permissions.

##### Email authentication

Email login availability is documented at the user-account level. However, `email-authentication.md` and `v8180-email-authentication.md` mainly describe administrator SMTP/authentication setup, not what an end user clicks or which email credential is accepted. If the login page is unclear, ask your administrator which option and credential to use.

##### External HTTP account

Raysync documents two permission models. If the external service controls permissions, its users are not created in Raysync and those accounts cannot log in to the Raysync system. If Raysync controls permissions, the external users are synchronized into Raysync and can use the external authentication service's username and password to log in.

#### Version differences

The supplied current and legacy email-authentication sources do not document different end-user steps. The two external HTTP permission models are also described consistently across the supplied versions.

#### Important notes

SMTP configuration also supports notifications and verification messages, so its presence does not prove that a separate email-login button is available. The sources do not document an end-user method to enable either authentication integration.

#### Sources

- `email-authentication.md` — “Email Authentication”
- `external-http.md` — “External Http Authentication”
- `v8180-email-authentication.md` — “Email”
- `v8180-external-http.md` — “External Http Authentication”
- `local-user.md` — “Local User” account-level email login availability
- `v8180-users.md` — “Users” account-level email login availability

### FAQ-START-011 | How do I sign out of Raysync?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Logout
- User intent: End the current user session
- Keywords: log out, sign out, switch account, exit client, profile

#### Short answer

In the user portal, select your username in the upper-right corner and choose **Log Out**. In the desktop client, open **Profile** and select **Switch Account** to log out of the current account and sign in with another one.

#### Version differences

The sources do not document a version-specific change to the user portal logout flow. The current desktop-client guide distinguishes switching accounts from exiting the program.

#### Important notes

Logging out is not the same as shutting down the desktop client. **Switch Account** logs out the current account. **Exit Client** closes the Raysync client. The user portal **Log Out** action ends the web session, but a running client may remain active until you log out or exit there as appropriate.

#### Sources

- `profile.md` — “User Log Out”
- `cloud.md` — “Profile”

### FAQ-START-012 | Which browser should I use with the Raysync user portal?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.3 and later
- Feature: Browser compatibility guidance
- User intent: Choose a browser for the user portal
- Keywords: browser, Google Chrome, user portal, compatibility

#### Short answer

For version 8.1.8.3 and later, use Google Chrome for the Raysync user portal. The current user profile guide recommends Chrome and displays a usage tip when a non-Chrome browser is used.

#### Version differences

`release.md` identifies **Browser Usage Tips** as a user-visible addition in version 8.1.8.3. The supplied sources do not establish the same recommendation for earlier versions, provide a supported-browser matrix, or state that every non-Chrome browser is unsupported.

#### Important notes

The browser affects the user portal, while accelerated browser-based transfer may also depend on the Raysync browser plug-in. If the plug-in is not installed or started, Raysync can switch to web TCP mode for a limited set of operations; this does not change the recommendation to use Chrome.

#### Sources

- `profile.md` — “Browser Usage Tips”
- `files.md` — “Start the client”
- `release.md` — version 8.1.8.3 “Browser Usage Tips”
