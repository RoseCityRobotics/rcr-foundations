# Cursor AI editor

**Cursor** is an AI‑powered code editor that integrates ChatGPT into a
Visual Studio Code–like environment.  It is free for personal use and
available for macOS, Windows and Linux.  Students should install
Cursor on their own laptops to benefit from AI‑assisted coding while
developing firmware and robotics software.

## macOS installation

1. Download the latest macOS installer (`Cursor.dmg`) from
   [cursor.sh](https://cursor.sh/).
2. Open the downloaded `.dmg` file and drag the **Cursor** icon into
   the **Applications** folder【570490748003363†L294-L304】.
3. Launch Cursor from Applications.  If macOS blocks the app because
   it is from an unidentified developer, open **System Settings →
   Security & Privacy**, click **Open Anyway** and confirm【570490748003363†L294-L304】.

## Windows installation

1. Download the Windows installer (`Cursor‑Setup.exe`) from
   [cursor.sh](https://cursor.sh/).
2. Double‑click the installer, accept the license agreement and choose
   the installation location and any additional tasks (e.g., create a
   desktop shortcut)【570490748003363†L266-L293】.
3. Click **Install** and then **Finish**.  Cursor will launch
   automatically.  Future updates are downloaded and installed
   automatically【570490748003363†L266-L293】.

## Linux (AppImage) installation

Cursor provides an AppImage for Linux distributions.  The following
steps are adapted from community guides【839571012710736†L62-L112】:

```bash
# download the AppImage (replace x64 with the architecture if needed)
wget "https://downloader.cursor.sh/linux/appImage/x64" -O cursor-latest.AppImage

# make it executable
chmod +x cursor-latest.AppImage

# run the AppImage
./cursor-latest.AppImage
```

The first launch may ask if you want to integrate Cursor into your
system menu and create a desktop shortcut【839571012710736†L103-L112】.  If
you encounter an error about `libfuse.so.2` missing, install the
library:

```bash
sudo apt update
sudo apt install libfuse2
```

Alternatively, run the AppImage with `--no-sandbox` to bypass sandbox
restrictions【839571012710736†L145-L151】.  Some users move the AppImage to
`~/Applications` and create a `.desktop` file for a more integrated
experience【839571012710736†L155-L186】.

## First steps and training

When you launch Cursor, it prompts you to log in with your GitHub
account and optionally import settings and extensions from VS Code.
You can then open a folder or file and start coding.  Use
**Cmd+K Cmd+I** (macOS) or **Ctrl+K Ctrl+I** (Windows/Linux) to
trigger Cursor’s AI suggestions within your code.

Cursor’s creators publish tutorial videos on their website and
YouTube.  See the official **Cursor Docs** and **Getting Started**
videos at <https://cursor.sh/docs> and
<https://www.youtube.com/@CursorAI>.

Installing Cursor alongside your regular editor gives you a powerful
assistant for writing firmware, scripts and documentation.