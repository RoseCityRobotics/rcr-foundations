# First boot & headless SSH

After flashing Ubuntu, power up your Raspberry Pi 5.  If you connected
a monitor, keyboard and mouse, Ubuntu’s installer will guide you
through first‑boot setup.  If you enabled headless options in Raspberry
Pi Imager, skip to the SSH section.

## Desktop configuration

1. **Language and keyboard.**  Choose your preferred language and
   keyboard layout.
2. **Region and time zone.**  Select your location to set the correct
   time zone【965428853420716†L206-L269】.
3. **User account.**  Create a username and a strong password.
4. **Updates and third‑party software.**  Decide whether to install
   updates and media codecs.  Ubuntu then finalises the installation.
5. **Login.**  Once the system reboots, log in with the account you
   created and finish any remaining prompts【965428853420716†L206-L269】.

## Headless SSH setup

If you enabled SSH in the Imager, you can connect from your laptop
without connecting a monitor.

1. **Find the IP address.**  Check your router’s device list or use
   `ping`/`nmap` to discover the Pi’s IP.
2. **SSH into the Pi:**

   ```bash
   ssh <username>@<ip-address>
   ```

   On first connection, you will see a host key fingerprint.  Type
   `yes` to continue.  Enter your password when prompted.  You will
   then see the Ubuntu command prompt【102108394223886†L1273-L1294】.

3. **Change the default password** (if you left the default) using
   `passwd` and update the system:

   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

From here you can proceed to install additional software and configure
the Pi for your projects.