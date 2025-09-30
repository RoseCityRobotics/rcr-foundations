# Imaging & flashing

Working with embedded systems often involves flashing disk images onto
removable media or microcontrollers.  This folder contains guides for:

* Writing Ubuntu or other OS images to microSD cards for Raspberry Pi.
* Flashing firmware images to microcontrollers such as Teensy.

## Guides

1. **[Flash a Raspberry Pi disk image](01-pi-disk-image.md)** – Use
   Raspberry Pi Imager or the `dd` command to write an OS image to a
   microSD card or USB/NVMe drive.
2. **[Flash Teensy firmware](02-flash-teensy.md)** – Use
   `teensy_loader_cli` to upload a compiled `.hex` file to your
   Teensy board (this is similar to the Microcontrollers guide but
   broken out here for quick reference).

These guides complement the microcontroller section and the Pi
installation instructions.  Always verify you are flashing to the
correct device to avoid data loss.