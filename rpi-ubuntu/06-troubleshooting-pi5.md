# Troubleshooting Raspberry Pi 5 on Ubuntu 24

Running a full desktop OS on a small computer can occasionally
introduce issues.  Here are some common problems and solutions.

## Performance feels slow or throttled

If Ubuntu 24 appears sluggish on your Pi 5, check your power supply.
Pi 5 requires a 5 V/5 A USB‑C supply; some third‑party adapters may
trigger a current limit.  Pi My Life Up notes that Ubuntu 24 imposes
stringent power checks which can throttle the CPU【29†L59-L67】.  Use the
official power supply or override the limit if you know your supply is
adequate【29†L73-L81】.  Updating firmware and Ubuntu (`sudo apt
upgrade`) may also resolve throttling.

## Display issues

If you see a green screen or no signal, try a different HDMI cable
and port.  Some users report needing to update the firmware or kernel
to fix video playback problems.  Run `sudo apt update` and
`sudo apt full-upgrade` to get the latest kernel.

## Networking problems

If SSH or networking fails, verify the Pi’s IP address (`hostname -I`)
and ensure it is connected to your router.  Check the status of
NetworkManager with `nmcli`.  Rebooting the Pi and your router often
resolves connectivity glitches.

## General diagnostics

Useful commands:

```bash
uname -a                 # kernel version
vcgencmd measure_temp    # CPU temperature (if vcgencmd is installed)
top or htop             # monitor CPU and memory usage
journalctl -p err -b     # view errors from current boot
```

For hardware questions, search the Raspberry Pi forums or AskUbuntu.
Community members regularly post fixes and workarounds for Pi 5
specific issues.