# Add Teensy board support

The Arduino CLI does not include support for PJRC’s **Teensy** boards by
default.  You must add PJRC’s package index and install the Teensy
core before you can compile sketches for boards like the Teensy 4.1.

## Initialise the Arduino CLI configuration

If this is your first time using Arduino CLI, create a configuration
file:

```bash
arduino-cli config init
```

This generates `~/.arduino15/arduino-cli.yaml` on Linux.  Edit this
file and add PJRC’s package URL under `board_manager.additional_urls`:

```yaml
board_manager:
  additional_urls:
    - https://www.pjrc.com/teensy/package_teensy_index.json
```

Save and exit.  Next, update the board index and install the Teensy
core:

```bash
arduino-cli core update-index
arduino-cli core search teensy     # optional: list available cores
arduino-cli core install teensy:avr
```

These commands fetch the latest package metadata, optionally list
available Teensy cores, and install the AVR core which supports
Teensy 4.x and earlier models【477523162427482†L120-L146】.

You are now ready to compile sketches for your Teensy board.  The
next guide shows how to compile and upload firmware.