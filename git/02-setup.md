# Setup

Before using Git you need to install it and configure your identity.

## Install Git

* **Ubuntu / Raspberry Pi:**

  ```bash
  sudo apt update
  sudo apt install -y git
  ```

* **macOS:** Install the Xcode Command Line Tools by running
  `xcode-select --install` or use Homebrew:

  ```bash
  brew install git
  ```

* **Windows:** Download and install **Git for Windows** from
  [gitforwindows.org](https://gitforwindows.org/).  During setup you
  can choose to use Git Bash, which provides a Unix‑like terminal.

After installation, verify the version:

```bash
git --version
```

## Configure your identity

Git stores your name and email in each commit.  Set them globally so
every new repository inherits these values:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

It is also common to set your default branch name to `main`:

```bash
git config --global init.defaultBranch main
```

To see all global settings:

```bash
git config --list --global
```

With Git installed and configured, you are ready to start using it.

## Learn more

For a quick visual walkthrough of getting started with Git, watch:
* [Get Going with Git](https://git-scm.com/videos) (4:26) – Quick start guide covering installation and basic setup
