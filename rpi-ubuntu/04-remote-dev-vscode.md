# Remote development with VS Code

Writing code directly on the Raspberry Pi can be slow and inconvenient
if you have a more powerful laptop.  Visual Studio Code’s **Remote
SSH** extension lets you develop on your Pi from your laptop as if
the files were local.

## Prerequisites

* A working SSH connection to your Pi (see the headless SSH guide).
* VS Code installed on your laptop.
* The **Remote SSH** extension (install from the VS Code Marketplace).

## Steps

1. On your laptop, open VS Code and install the **Remote SSH**
   extension (search for "Remote – SSH" in Extensions).
2. Ensure your Pi is reachable via SSH.  You may want to set up an
   entry in `~/.ssh/config`:

   ```
   Host rpi5
     HostName 192.168.1.42
     User pi
   ```

3. In VS Code, press **F1** and type `Remote‑SSH: Connect to Host…`.
   Select `rpi5` (or enter `user@ip`).  VS Code opens a new window
   connected to the remote host and installs the server component
   automatically【25†L35-L38】.
4. Once connected, click **Open Folder** and choose a directory on
   the Pi (e.g., `/home/pi/projects`).  VS Code displays the folder
   contents in its Explorer pane and you can open, edit and save files
   seamlessly【25†L33-L39】.

This setup allows you to use your laptop’s CPU and screen while
executing code on the Pi.  You can also use integrated terminals,
debuggers and extensions on the remote host.