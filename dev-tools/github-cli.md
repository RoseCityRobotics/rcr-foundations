# GitHub CLI: installation and basics

The **GitHub CLI** (`gh`) extends Git by allowing you to interact with
GitHub repositories and workflows directly from your terminal.  It is
particularly useful when working on open‑source projects or submitting
assignments via pull requests.

## Installation

Install `gh` on your personal machine (not the Raspberry Pi) using the
method appropriate for your OS.  These steps mirror the Git section’s
instructions【144619821729735†L355-L368】:

* **Ubuntu / Debian:** Add the GitHub apt repository and install via
  `sudo apt install gh`【144619821729735†L355-L368】.
* **macOS:** Use Homebrew: `brew install gh` and upgrade with
  `brew upgrade gh`【144619821729735†L462-L468】.
* **Windows:** Use winget: `winget install -e --id GitHub.cli`
 【908978899632431†L40-L44】.  Open a new terminal after installation so the
  PATH is updated.

See [git/07-github-cli.md](../git/07-github-cli.md) for the full apt
repository commands, including GPG key configuration.

## Authenticate

Run `gh auth login` to connect the CLI to your GitHub account.  Select
GitHub.com and follow the interactive prompts.  If you choose HTTPS
for Git operations, the CLI can store your Git credentials so you
don’t need to set up SSH keys【493090183611143†L65-L81】.

## Common commands

Use `gh` in your Git repositories:

```bash
gh repo create           # create a new repo on GitHub
gh issue list            # list issues
gh pr create             # open a pull request
gh pr status             # view PR status
gh auth status           # verify authentication
```

Run `gh help` or `gh <command> --help` to explore more functionality.

Integrate `gh` into your workflow to speed up tasks that would
otherwise require visiting the GitHub website.