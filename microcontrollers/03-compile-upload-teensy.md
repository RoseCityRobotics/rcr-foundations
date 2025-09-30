# Compile and upload Teensy firmware

With Arduino CLI installed and the Teensy core added, you can compile
your sketch for a specific board and upload it using PJRC’s
`teensy_loader_cli` tool.

## Compile a sketch

To compile a sketch, you must specify the **Fully Qualified Board Name**
(FQBN) of your Teensy board.  For example, to compile `blink.ino` for
the Teensy 4.1:

```bash
arduino-cli compile --fqbn teensy:avr:teensy41 --output-dir build blink
```

Replace `teensy41` with the appropriate board (e.g., `teensy40` for
Teensy 4.0).  The compiled `.hex` file will be placed in the
`build` directory【477523162427482†L167-L183】.

## Upload using teensy_loader_cli

PJRC provides a command‑line loader for Teensy boards.  Install
`teensy_loader_cli` from your distribution’s package manager or
download a prebuilt binary from PJRC’s website.  To upload a compiled
hex file:

```bash
teensy_loader_cli --mcu=TEENSY41 -w build/blink.ino.hex
```

Replace `TEENSY41` with the correct MCU value for your board
(e.g., `TEENSY40`, `TEENSY36`, etc.) and adjust the path to the hex
file.  The `-w` option tells the loader to wait for the device to
appear【10116716418159†L24-L60】.  Other useful flags include:

* `-r` – hard reboot after uploading.
* `-s` – soft reboot (leaves the bootloader running).
* `-n` – no reboot (useful for certain workflows).
* `-v` – verbose output.

When the loader completes, your Teensy will run the new firmware.

## Automating the process

You can write a shell script that compiles and uploads in one step:

```bash
#!/usr/bin/env bash
set -euo pipefail
BOARD=teensy41
SKETCH=blink
BUILD_DIR=build

arduino-cli compile --fqbn teensy:avr:$BOARD --output-dir "$BUILD_DIR" "$SKETCH"
teensy_loader_cli --mcu=${BOARD^^} -w "$BUILD_DIR/$SKETCH.ino.hex"
```

This script sets the board type, compiles the sketch and uploads it.
Note that `${BOARD^^}` converts the board name to uppercase for the
`--mcu` flag.