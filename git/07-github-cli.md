# GitHub CLI (`gh`)

The **GitHub CLI** is an official command‑line tool that lets you
interact with GitHub from your terminal.  You can create issues and
pull requests, review code, view notifications, and even clone
repositories without leaving the command line.

## Installation

### Ubuntu / Debian / Raspberry Pi

GitHub provides a package repository for Debian‑based systems.  On
Ubuntu 24 or Raspberry Pi OS, run the following commands to install
`gh`:

```bash
sudo apt update && sudo apt install -y wget gpg
sudo mkdir -p /etc/apt/keyrings
wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg \
  | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg >/dev/null
echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] \
  https://cli.github.com/packages stable main" \
  | sudo tee /etc/apt/sources.list.d/github-cli.list >/dev/null
sudo apt update
sudo apt install -y gh
```

This sequence downloads the GPG key, configures the repository and
installs the `gh` package【144619821729735†L355-L368】.  After installation you
can update `gh` through `apt upgrade`.

### macOS (Homebrew)

On macOS you can install the CLI with Homebrew:

```bash
brew install gh
```

If `gh` is already installed, upgrade it with `brew upgrade gh`【144619821729735†L462-L468】.

### Windows (Winget)

The recommended way to install GitHub CLI on Windows is via
**winget**:

```powershell
winget install -e --id GitHub.cli
```

This command downloads and installs `gh` and adds it to your PATH【908978899632431†L40-L44】.
Open a new terminal after installation so the PATH changes take effect.

## Authentication and usage

To authenticate the CLI with your GitHub account, run:

```bash
gh auth login
```

Choose **GitHub.com** (or GitHub Enterprise if applicable) and follow
the prompts.  You can authenticate via a browser or a device code.
When asked whether to authenticate Git with your GitHub credentials,
answer **Yes** if you want Git to use a personal access token for
`git push` and `git pull`【493090183611143†L65-L81】.  The CLI stores your
credentials securely, so you don’t need to configure SSH keys unless
you prefer them.

Once logged in, try:

```bash
gh repo create         # create a new repository
gh issue list          # list open issues
gh pr status           # view pull request status
gh pr create           # create a pull request
```

Use `gh help` to explore all available commands.