# Install Arduino CLI

The Arduino command‑line interface (*Arduino CLI*) is a headless version of the Arduino IDE that supports core and library management, compilation and uploading.  It’s perfect for scripting builds on headless systems like Raspberry Pi.

## On Ubuntu and Raspberry Pi

The easiest way to install Arduino CLI on Ubuntu (including Raspberry Pi 5 running Ubuntu 24) is via the official install script:

```bash
cd ~
curl -fsSL https://raw.githubusercontent.com/arduino/arduino-cli/master/install.sh | sh
```

If your system does not have `curl` installed (Ubuntu Server omits it by
default), first install it with `sudo apt install curl`【28†L139-L146】.
Alternatively, you can download the script using `wget`:

```bash
wget -qO- https://raw.githubusercontent.com/arduino/arduino-cli/master/install.sh | sh
```

This script downloads the latest release appropriate for your architecture and places the `arduino-cli` binary in `$PWD/bin`【641133880484485†L123-L144】.  To use the command anywhere, add this directory to your `PATH`, for example in `~/.bashrc`:

```bash
export PATH="$PATH:$HOME/bin"
```

Alternatively, you can specify a different install directory by setting the `BINDIR` environment variable when running the install script【641133880484485†L129-L144】:

```bash
BINDIR=/usr/local/bin curl -fsSL https://raw.githubusercontent.com/arduino/arduino-cli/master/install.sh | sh
```

After installation, verify the version:

```bash
arduino-cli version
```

This command should print the CLI version number, confirming a successful installation.

## On macOS and Linux via Homebrew

If you use Homebrew on macOS or Linux, you can install Arduino CLI directly from the `homebrew-core` tap:

```bash
brew update
brew install arduino-cli
```

Arduino CLI has been available as a Homebrew formula since version 0.5.0【641133880484485†L89-L100】.  After installation, the CLI binary is available on your `PATH`.

## On Windows

For Windows users, pre‑built installers (MSI) and executables are provided on the Arduino CLI releases page【641133880484485†L180-L206】.  Download the appropriate `arduino-cli_version_Windows_x86_64.msi` file, run it, and follow the prompts.  If you prefer manual installation, download the `.zip` archive, extract it, and add the extracted directory to your `PATH`.

Once the CLI is installed, you’re ready to add board support and compile sketches.