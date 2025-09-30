# Microcontrollers: Arduino CLI and Teensy

This folder contains guides for setting up microcontroller development on your Raspberry Pi 5 running Ubuntu 24.  We use the **Arduino CLI** to compile and upload code to **Teensy** microcontrollers.  These boards are used in many robotics and control systems projects because they combine ARM‑class power with the simplicity of the Arduino ecosystem.

## Guides

1. **[Install Arduino CLI](01-arduino-cli-install.md)** – Install the Arduino command‑line interface (CLI) on Ubuntu, macOS or Windows via Homebrew or the official install script.  The CLI provides the same board and library managers as the graphical IDE【641133880484485†L86-L100】.
2. **[Add Teensy board support](02-teensy-board-support.md)** – Configure Arduino CLI with PJRC’s board manager URL and install the Teensy core so that you can compile sketches for boards like the Teensy 4.1【477523162427482†L120-L146】.
3. **[Compile and upload Teensy firmware](03-compile-upload-teensy.md)** – Use Arduino CLI to compile a sketch for a specific Teensy board and upload the resulting `.hex` file to the microcontroller using the `teensy_loader_cli` tool【10116716418159†L24-L60】.

These guides assume you are working on a Raspberry Pi or other Linux machine where you will build and flash firmware.  For Windows or macOS development, see the Arduino CLI installation notes within the first guide.