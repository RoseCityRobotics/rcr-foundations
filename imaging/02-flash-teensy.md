# Flash a Teensy microcontroller

This guide summarises the process of uploading a compiled firmware
image to a **Teensy** microcontroller using the command‑line loader.
For a full workflow including compilation, see the microcontrollers
section.

## Prerequisites

* A compiled `.hex` or `.elf` file (created with Arduino CLI).
* `teensy_loader_cli` installed on your PC or Raspberry Pi.

## Uploading the firmware

1. Connect your Teensy board to your computer via USB.  Ensure the
   board is in bootloader mode (press the reset button if needed).
2. Run the loader specifying the correct MCU and the hex file.  For
   example, to upload firmware to a Teensy 4.1:

   ```bash
   teensy_loader_cli --mcu=TEENSY41 -w path/to/firmware.hex
   ```

   The `-w` flag tells the loader to wait for the device to appear
   before uploading【10116716418159†L24-L60】.

3. After the upload completes, the Teensy reboots and runs the new
   firmware.  You can add `-v` for verbose output or `-r` to force a
   hard reboot【10116716418159†L24-L60】.

## Tips

* If you see a connection error, press the Teensy’s reset button to
  enter bootloader mode and try again.
* Make sure you specified the correct MCU for your board (e.g.,
  `TEENSY40`, `TEENSY36`, etc.).
* See `teensy_loader_cli --help` for more options.  The man page
  provides a summary of all flags and supported boards【10116716418159†L24-L60】.

Uploading firmware via the command line integrates nicely into
automated build scripts and continuous integration pipelines.