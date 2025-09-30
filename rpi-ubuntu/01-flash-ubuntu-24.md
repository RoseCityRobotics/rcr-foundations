# Flash Ubuntu 24.04 LTS onto a microSD or SSD

These instructions walk you through flashing **Ubuntu 24.04 LTS**
(Desktop or Server) to a microSD card or USB/NVMe drive for your
Raspberry Pi 5.  Ubuntu 24.04 is fully supported and hardware
certified for the Pi 5【21†L139-L147】.

## What you need

* Raspberry Pi Imager (latest version) installed on your laptop.
* A microSD card (32 GB or larger) or USB/NVMe drive with enough
  capacity.  All data on the drive will be erased.

## Steps

1. **Insert the storage device** into your computer.  Back up any
   existing data.
2. **Open Raspberry Pi Imager.**  Click **Choose Device** and select
   *Raspberry Pi 5*.  Then click **Choose OS** → **Other general
   purpose OS** → **Ubuntu** and select **Ubuntu 24.04 LTS** (Desktop
   or Server)【965428853420716†L135-L196】.
3. **Choose Storage.**  Select your microSD card or USB/NVMe drive.
4. *(Optional)* Click the gear icon to access **Advanced options**.
   Here you can set the hostname, username/password, Wi‑Fi details and
   enable SSH for headless setup【34†L142-L150】.
5. **Write.**  Click **Next** and confirm that you want to erase the
   storage device.  The imager downloads the Ubuntu image and writes
   it.  This may take several minutes【965428853420716†L135-L196】.
6. **Eject the drive.**  When complete, remove the drive and insert it
   into your Raspberry Pi 5.  If using an NVMe, connect it via a
   compatible HAT or USB adapter.

On first boot, follow the [first‑boot guide](02-first-boot-headless.md)
to configure Ubuntu.  If you enabled SSH, you can boot headless and
connect from your laptop without a monitor.