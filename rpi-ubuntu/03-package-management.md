# Package management (APT) and missing tools

Ubuntu uses the **APT** package manager to install, update and remove
software.  Knowing a few commands helps you keep your system secure
and install new utilities.

## Update and upgrade

Run this command regularly to fetch the latest package lists and
upgrade installed software:

```bash
sudo apt update && sudo apt upgrade -y
```

## Install packages

If a command like `curl` or `git` is missing, install it with `apt`:

```bash
sudo apt install -y curl git build-essential htop nano vim
```

On minimal Ubuntu Server installs, `curl` may not be present.  The fix
is straightforward: use `apt` to install it【28†L139-L146】.

## Search for packages

Use `apt search` or `apt-cache` to find packages by name:

```bash
apt search python3
apt-cache policy docker-ce
```

## Remove packages

To remove a package and its configuration files:

```bash
sudo apt purge name-of-package
```

To clean up unused dependencies and cached files:

```bash
sudo apt autoremove --purge
sudo apt clean
```

Understanding `apt` will make it easier to install development tools
and troubleshoot missing dependencies on your Pi.