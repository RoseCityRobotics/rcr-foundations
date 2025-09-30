# Flash a Raspberry Pi disk image

There are two common ways to write an operating system image to a
microSD card or USB/NVMe drive for your Raspberry Pi: using the
Raspberry Pi Imager (recommended for most users) or using the
`dd` command (for advanced users on Linux/macOS).

## Method 1: Raspberry Pi Imager (GUI)

Follow the steps outlined in the Pi My Life Up guide【965428853420716†L135-L196】:

1. Install Raspberry Pi Imager on your laptop.
2. Insert your microSD card or USB/NVMe drive.
3. Launch the Imager and click **Choose Device** → select your
   Raspberry Pi model (e.g., Pi 5).
4. Click **Choose OS** → **Other general purpose OS** → **Ubuntu** and
   select the desired version (e.g., **Ubuntu 24.04 LTS Desktop**).
5. Click **Choose Storage** and select your card or drive.
6. *(Optional)* Click the gear icon for advanced options: set
   hostname, enable SSH, configure Wi‑Fi and set a default user
   account【34†L142-L150】.
7. Click **Next** (or **Write**) and confirm you want to erase the
   drive.  The imager downloads and writes the image; this takes
   several minutes【965428853420716†L135-L196】.
8. When finished, eject the drive and insert it into your Raspberry Pi.

For first‑boot setup, see the [Raspberry Pi Ubuntu guide](../rpi-ubuntu/02-first-boot-headless.md).

## Method 2: `dd` command (CLI)

On Linux or macOS, experienced users may prefer `dd` to flash an
image.  **Use caution**: choosing the wrong device can destroy data.

1. Download the Ubuntu image (`.img.xz`) and uncompress it if needed.
2. Identify the device path of your SD card (e.g., `/dev/sdX` or
   `/dev/disk2`).  Use `lsblk` (Linux) or `diskutil list` (macOS).
3. Unmount the device.  For example, on macOS:

   ```bash
   diskutil unmountDisk /dev/disk2
   ```

4. Use `dd` to write the image (replace paths accordingly):

   ```bash
   sudo dd if=ubuntu-24.04-preinstalled-server-arm64+.img of=/dev/rdisk2 bs=4m status=progress
   sync
   ```

   * `if`: input file (the image).
   * `of`: output device.
   * `bs=4m`: block size (adjust for speed).
   * `status=progress`: show progress.
   * `sync`: flush disk caches when done.

5. After `dd` finishes, eject the card with `diskutil eject /dev/disk2` (macOS) or `umount` (Linux) and insert it into your Pi.

When in doubt, use the Raspberry Pi Imager; it reduces the risk of
overwriting the wrong drive.