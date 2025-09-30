# PuTTY: Terminal and SSH on Windows

PuTTY is a free, MIT‑licensed SSH/Telnet client that provides a simple way to open a remote terminal on your Raspberry Pi from a Windows PC.  Below you’ll find installation instructions, connection tips and shortcuts for efficient use.

## Install PuTTY (latest version)

1. Visit the official PuTTY download page and download the Windows installer matching your system architecture.  As of February 2025 the latest stable release is **PuTTY 0.83**【712716679086993†L7-L34】.  Choose the 64‑bit installer (`putty‑64bit‑0.83‑installer.msi`) for modern Windows systems or the 32‑bit installer for older machines【712716679086993†L32-L41】.
2. Double‑click the `.msi` file to launch the installer and follow the on‑screen prompts.  The installer copies PuTTY and its companion tools (PSCP, PSFTP, Plink, Pageant, PuTTYgen) to `C:\Program Files\PuTTY` and adds them to your Start menu.
3. Optionally, install PuTTY via the Microsoft Store.  The PuTTY team publishes the latest release on the Store a few days after release【712716679086993†L28-L31】.

## Create and open an SSH session

PuTTY works by configuring a *session* and then opening that session.  To connect to your Raspberry Pi:

1. Launch PuTTY from the Start menu.  A configuration window appears.
2. In the **Host Name (or IP address)** field, enter your Pi’s IP, for example `192.168.1.42`.
3. Ensure the **Port** is `22` and **Connection type** is **SSH**.  These defaults are correct for most setups【928148377421320†L531-L544】.
4. (Optional) Under *Saved Sessions*, type a name like `robot‑pi` and click **Save** so you don’t have to retype the IP later.
5. Click **Open** to initiate the connection.  On first connection PuTTY displays a security alert that the server’s host key is not cached; click **Yes** to trust it.
6. A black terminal window appears prompting for your username and password【928148377421320†L474-L516】.  Enter your Pi’s username (often `ubuntu`, `pi` or your custom user) and password.  Upon success you’ll see a command prompt and can run Linux commands remotely.

## Copy and paste in PuTTY

PuTTY emulates Unix `xterm` behaviour for copy and paste.  These shortcuts differ from typical Windows editors:

- **Copy:** Click the left mouse button and drag to select text.  When you release the button, the selected text is automatically copied to the Windows clipboard【689115589285535†L42-L48】.  Do **not** press `Ctrl+C` or `Ctrl+Ins`—PuTTY interprets these as sending a `Ctrl-C` to the remote application【689115589285535†L47-L49】.
- **Paste:** Click the right mouse button to paste the clipboard contents into your terminal.  You can also press `Shift+Ins` or select **Paste** from the context menu【689115589285535†L51-L55】.
- **Word/line select:** Double‑click selects an entire word; triple‑click selects a whole line【689115589285535†L64-L68】.
- **Rectangular selection:** Hold `Alt` while dragging to select a column of text【689115589285535†L70-L73】.

Being aware of PuTTY’s mouse‑based copy/paste avoids accidentally sending `Ctrl+C` to a running process.  If you prefer keyboard shortcuts, PuTTY can be configured to permit `Ctrl+Shift+C/V` in **Window → Selection** settings.

## Session management and tips

- **Saved sessions:** Use the *Saved Sessions* list in the main PuTTY window to store multiple Raspberry Pi or server connections.  Select a session and click **Load** to populate its settings.
- **Keepalives:** On unreliable networks, set *Connection → Seconds between keepalives* to a value like `60` to prevent timeouts.
- **Fonts and colours:** Adjust the appearance under *Window → Appearance*.
- **Pageant for keys:** If you use SSH keys instead of passwords, run `pageant.exe` (installed alongside PuTTY) to load your private key once and authenticate automatically.  Generate keys using `puttygen.exe` (also installed).

With PuTTY configured, your Windows machine becomes a powerful remote terminal for working on your Raspberry Pi and other Linux systems.