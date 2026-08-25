# Client Installation and Settings

### FAQ-CLIENT-001 | How do I download the Raysync client?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; Linux desktop client from version 8.1.8.2
- Feature: Client download
- User intent: Obtain the correct installer
- Keywords: client download, installer, desktop client, browser plug-in, platform

#### Short answer

Sign in to the user portal. If the client is not installed or started, select **Client Download**, choose the package for your platform and preferred client type, and download it. Raysync offers a desktop client for high-speed transfers without keeping the web page open and a browser plug-in for accelerated transfers initiated from the user portal.

#### Steps

1. Open the Raysync user portal.
2. Select **Client Download** when prompted or from the portal's client controls.
3. Choose the desktop client or browser plug-in and the package for your operating system.
4. Run the downloaded installer.

#### Version differences

The Linux desktop client became available in version 8.1.8.2. The release history does not identify a different download procedure for later releases.

#### Important notes

Use the package presented by your own Raysync server. A deployment may customize its client download URL, and an incorrect customized URL can affect normal startup from the user portal.

#### Sources

- `files.md` — “Download client” and “Desktop Client: Linux Version Now Available”
- `create-task.md` — “Download the client”
- `configuration.md` — “Client settings”
- `release.md` — version 8.1.8.2 Linux client release

### FAQ-CLIENT-002 | What is the difference between the desktop client and the browser plug-in?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Client modes
- User intent: Choose a transfer client
- Keywords: desktop client, browser plug-in, web transfer, high-speed transfer

#### Short answer

Choose the desktop client when you want a standalone high-speed interface that does not require the web page. Choose the browser plug-in when you want to select content in **My Files** or **Group File Folder** in the user portal and have the installed plug-in accelerate that portal-initiated transfer.

Both are installed components. This FAQ is about which component to install; web TCP versus client transfer mode is a separate transfer-mode decision.

#### Version differences

Version 8.1.8.0 added multiple authentication methods to the browser plug-in. Version 8.1.8.4 added desktop-client handling of Raysync links. These additions do not change the basic division between standalone desktop-client use and plug-in-assisted web use.

#### Important notes

The browser plug-in still depends on the user portal, while the desktop client has its own transfer interface. If your administrator offers only one package or limits the allowed transfer type, use the available component.

#### Sources

- `create-task.md` — “Download the client” and “Start transfer”
- `files.md` — “Download client,” “Start the client,” and “File Operations”
- `release.md` — version 8.1.8.0 and version 8.1.8.4 client changes

### FAQ-CLIENT-003 | How do I install Raysync on Windows?

- Product: Raysync
- Audience: End user
- Applies to: Documented Windows platforms
- Feature: Windows installation
- User intent: Install the desktop client or browser plug-in
- Keywords: Windows, install, desktop client, browser plug-in, installer

#### Short answer

Download the appropriate Windows client package from the user portal, double-click the installer, select the requested options and installation path, and finish the installation.

#### Steps

For the desktop client:

1. Double-click the downloaded installer.
2. Select the installation options and choose **Next**.
3. Select the installation path and choose **Install**.
4. Choose **Finish** to run the desktop client.

For the browser plug-in, accept the software agreement, choose **Next**, select the components and path, choose **Install**, and then **Finish**.

#### Version differences

The source does not document a changed Windows installer sequence across the listed versions.

#### Important notes

The documented platform statement lists Windows Server 2008, Windows Server 2012, Windows Server 2016, Windows 7, Windows 8, and Windows 10. It does not provide a statement for other Windows releases, so confirm unsupported or newer platforms with your administrator.

#### Sources

- `files.md` — “Client installation and uninstallation” and “Install the client”
- `cloud.md` — “Install the client”

### FAQ-CLIENT-004 | How do I install Raysync on macOS?

- Product: Raysync
- Audience: End user
- Applies to: macOS 10.11 and above as documented
- Feature: macOS installation
- User intent: Install a Mac client
- Keywords: macOS, Mac, install, client package

#### Short answer

From the Raysync user portal, select **Client Download**, choose the package for macOS, open the downloaded package, and follow its installer prompts. The source documentation states that the Raysync client supports macOS 10.11 and above.

#### Steps

1. Open your organization's Raysync user portal.
2. Select **Client Download**.
3. Choose the client package for macOS.
4. Open the downloaded package and complete the presented installation flow.

#### After installation

Start the installed client. Signing in is a separate post-install action: enter the Raysync server address and then your account and password as documented by the desktop-client login guide.

#### Version differences

The sources do not identify a macOS version boundary or a different macOS installation procedure within the documented Raysync releases.

#### Important notes

The available guide provides the platform requirement but does not document macOS-specific dialog labels or security-approval steps. Follow the prompts in the package supplied by your server; do not assume the Windows screenshots apply to macOS.

#### Sources

- `files.md` — “Client installation and uninstallation,” “Download client,” and “Install the client”
- `cloud.md` — “Log in”

### FAQ-CLIENT-005 | Is the Raysync desktop client available for Linux?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.2 and later
- Feature: Linux desktop client
- User intent: Determine Linux availability
- Keywords: Linux, desktop client, availability, version 8.1.8.2

#### Short answer

Yes. Raysync documents a Linux version of the desktop client beginning with version 8.1.8.2. Download the Linux package offered by your Raysync user portal.

#### Version differences

`release.md` lists **Desktop Client: Linux Version Now Available** under version 8.1.8.2. Earlier platform text lists Windows and macOS client support but does not claim Linux desktop-client availability for those earlier releases.

#### Important notes

The supplied end-user source confirms Linux availability but does not list supported Linux distributions, package formats, or a Linux-specific installation sequence. Use the package and instructions supplied by your organization. Linux/Unix system authentication is a separate server-side authentication feature and is not the same as installing the Linux desktop client.

#### Sources

- `files.md` — “Desktop Client: Linux Version Now Available”
- `release.md` — version 8.1.8.2

### FAQ-CLIENT-006 | How do I start the Raysync client from the user portal?

- Product: Raysync
- Audience: End user
- Applies to: Documented Windows browser-launch workflow; manual macOS/Linux command not specified
- Feature: Client startup
- User intent: Launch the installed client
- Keywords: start client, Transfer List, raysync-watch.exe, client not connected

#### Short answer

On Windows, select **Transfer List** in the user portal. If the client is not connected, choose **Start** in the prompt, approve the browser request to open `raysync-watch.exe`, and wait for startup to finish. The same **Start** action is available when the portal displays a client-not-connected message.

#### Steps

1. On Windows, sign in to the user portal.
2. Select **Transfer List**, or use the **Start** button in a client-not-connected message.
3. When the browser asks whether to open `raysync-watch.exe`, allow it.
4. Wait until the client connection completes.

#### Version differences

No version-specific change to the documented Windows launch sequence is identified. The supplied source does not document an equivalent executable name or manual browser-start command for macOS or Linux.

#### Important notes

Allowing the browser prompt starts an already installed desktop client; it does not install the client.

#### Sources

- `files.md` — “Start the client”

### FAQ-CLIENT-007 | What is the default server setting in the Raysync client?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Default server
- User intent: Keep a client connected to a Raysync server
- Keywords: default server, server address, credentials, server task, client device

#### Short answer

The default server setting stores the Raysync server address, login username, and password used by the client. Enter the correct values in **Settings > Default server** and save them. The documented address example is `http://[server-IP]:8090`.

A configured default server also allows an administrator to identify the client device for monitoring and for administrator-issued server tasks.

#### Version differences

The available sources do not document a changed end-user default-server procedure at version 8.1.8.0.

#### Important notes

For an administrator-issued server task to run normally, the client must be started, logged in to the correct default server, and online. Use the address and credentials supplied by your administrator. Saving a wrong server address or account prevents the expected connection.

#### Sources

- `client.md` — “Default server”
- `server-task.md` — “The client configures the default server”
- `files.md` — “Install the client”

### FAQ-CLIENT-008 | How do I sign in from the Raysync desktop client?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Desktop-client login
- User intent: Connect the desktop client for transfer
- Keywords: desktop client, server address, account, password, login

#### Short answer

Start the desktop client, enter the Raysync server address, choose **Next** if shown, then enter your account and password and select **Log In**. The documented default address format is `http://[server-IP]:8090`.

#### Steps

1. Open the installed desktop client.
2. Enter the server address supplied by your administrator.
3. Select **Next**.
4. Enter your account and password.
5. Select **Log In** to connect and begin high-speed transfers.

#### Version differences

Version 8.1.8.0 added multiple authentication methods to the browser plug-in. That release note does not establish third-party authentication support for the desktop client. The desktop-client sources document only the server-address plus account-and-password flow.

#### Important notes

The server address may differ from the default example. Use the account and password supplied for desktop-client access. If your organization requires a third-party method, ask the administrator whether it applies only to the browser plug-in or whether a supported desktop-client procedure is available; the supplied desktop sources do not specify one.

#### Sources

- `cloud.md` — “Log in”
- `create-task.md` — “Start transfer”
- `files.md` — “Install the client”
- `release.md` — version 8.1.8.0 browser plug-in authentication change

### FAQ-CLIENT-009 | What happens when the client is unavailable during a web transfer?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions; web pause/cancel from version 8.1.8.1
- Feature: Web TCP fallback
- User intent: Transfer without a running client
- Keywords: web TCP, fallback, client unavailable, normal upload, normal download

#### Short answer

After you log in, the user portal checks whether the Raysync client is active. If it is not active, the portal automatically switches to web TCP connection mode. This fallback is automatic; you do not select it as a client component.

#### Version differences

Starting with version 8.1.8.1, the web interface allows users to pause or cancel web transfer tasks without the client. The source does not claim that this release adds the full client feature set to web mode.

#### Important notes

The fallback indicates that client acceleration and client-only functions are unavailable. It supports only the documented browser operations; start or install the client when the portal requires one. See the browser-only file-operations FAQ for the supported action list and its limitations.

#### Sources

- `files.md` — “Start the client,” “File Operations,” and “Upload file”
- `release.md` — version 8.1.8.1 web pause/cancel
- `v8180-transfer.md` — “Transfer” transfer-type choices

### FAQ-CLIENT-010 | Does the Raysync client upgrade automatically?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions when auto-update is enabled
- Feature: Client upgrade
- User intent: Understand update behavior
- Keywords: automatic upgrade, auto-update, version, default server, silent upgrade

#### Short answer

Two update behaviors are documented. With administrator-enabled auto-update, a correct default-server configuration, and a server version newer than the client version, the configuration guides say the client performs a silent upgrade. The cloud client guide separately says the client detects a new version and prompts the user to upgrade.

#### Version differences

The supplied sources do not explain whether silent upgrade and detect-and-prompt apply to different client builds, settings, or deployment types, and they do not specify which behavior takes precedence when both conditions exist.

#### Important notes

Keep the default-server connection correct. If an upgrade prompt appears, follow it; otherwise an enabled silent upgrade may require no action. To check manually, right-click the client, select **About**, view the client version, and check whether it is the latest Raysync version.

#### Sources

- `configuration.md` — “Client settings”
- `v8180-transfer.md` — “Client app”
- `cloud.md` — “Client setting”
- `client.md` — “About Raysync”

### FAQ-CLIENT-011 | How do I uninstall the Raysync client on Windows?

- Product: Raysync
- Audience: End user
- Applies to: Documented Windows installations
- Feature: Client uninstallation
- User intent: Remove the installed client
- Keywords: uninstall, Windows Control Panel, uninstall.exe, remove client

#### Short answer

Use Windows **Control Panel > Programs > Programs and Features**, select the Raysync client, and uninstall it. Alternatively, open the client installation directory and run `uninstall.exe` as administrator.

#### Steps

Method 1:

1. Open **Control Panel > Programs > Programs and Features**.
2. Select the Raysync client.
3. Right-click and choose uninstall.

Method 2:

1. Right-click the desktop Raysync icon and select **Open file location**.
2. Right-click `uninstall.exe` and select **Run as administrator**.
3. Confirm removal.

#### Version differences

No version-specific uninstall change is documented.

#### Important notes

These are Windows procedures. The available source does not provide macOS- or Linux-specific uninstall instructions. Exiting the client only closes it; it does not uninstall the software.

#### Sources

- `files.md` — “Uninstall the client”
- `cloud.md` — “Profile” for the separate Exit Client action

### FAQ-CLIENT-012 | How do I set the default download path?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Download path
- User intent: Choose where downloaded files are saved
- Keywords: download path, settings, save location, open file directory

#### Short answer

Open the client transfer settings and set **Download path** to the folder you want to use by default. Raysync also supports manually selecting a path when starting a download.

After a client download finishes, use **Open File Directory** in the browser plug-in or transfer list to locate the downloaded file.

#### Version differences

The documented setting is consistent across the user client and cloud guides. No release-specific change is identified.

#### Important notes

The default path applies to client downloads. A download performed with the web option appears in the browser's downloads and follows browser download behavior. Peer-to-peer transfer has a separate receive-file save path in the client settings.

#### Sources

- `client.md` — “Transfer” and “Peer-to-Peer” settings
- `cloud.md` — “Client setting”
- `files.md` — “Download file”

### FAQ-CLIENT-013 | How do I open and use the client transfer list?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Transfer list
- User intent: Monitor and manage client tasks
- Keywords: Transfer List, progress, speed, task details, pause, resume

#### Short answer

Select **Transfer List** in the upper-right corner of the user portal, select the client icon, or right-click the client and choose **Transfer List**. The list includes general transfer tasks, sync tasks, and peer-to-peer tasks.

Use the list to operate on client tasks: pause or start selected tasks, batch-select with `Ctrl` or `Ctrl+A`, delete a task, retry when available, pin a task, open its local directory, or open its details.

#### Version differences

Version 8.1.8.6 adds client task sorting and creation-time filtering. Version 8.1.8.7 adds filtering by task name and task status.

#### Important notes

The source does not fully define whether deleting an active client task both stops the transfer and removes its record. It does not state that task deletion deletes source or destination files. Use the client list only for client-task operations; web progress is shown elsewhere.

#### Sources

- `client.md` — “Transfer List”
- `cloud.md` — “General task”
- `release.md` — version 8.1.8.6 and version 8.1.8.7 client task-list changes

### FAQ-CLIENT-014 | How do I collect Raysync client logs for support?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Client logs
- User intent: Gather diagnostic information
- Keywords: collect logs, client log, support, retention, error detection

#### Short answer

Open the client settings, go to the log controls, and use the log collection action to collect the current day's client logs. Provide the collected logs to Raysync technical support for diagnosis.

The client supports a configurable log-retention period. Logs older than that period are cleared automatically, and the client automatically compresses logs during the day.

#### Version differences

The supplied sources do not document a version-specific change to the end-user action for collecting the current day's client logs.

#### Important notes

Collect the logs before the configured retention period removes them. Log collection gathers evidence for support; diagnosing a failed task and using **Error Detection** are covered separately in the transfer-failure FAQ.

#### Sources

- `client.md` — “Log Setting”
- `cloud.md` — “Client setting” log controls
