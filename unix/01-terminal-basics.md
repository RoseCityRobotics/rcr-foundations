# Terminal basics

Understanding the terminal is the first step toward using a UNIX system
effectively.  A **shell** is a program that reads your commands and
executes them.  Common shells include `bash`, `zsh` and `fish`; most
Linux distributions use Bash by default.

## Opening a terminal

* **macOS:** Launch **Terminal** from Applications → Utilities, or use
  **iTerm2** for a more feature‑rich replacement.
* **Linux:** Press **Ctrl + Alt + T** or open your system’s Terminal
  application.
* **Windows:** Use **Windows Terminal** with the Windows Subsystem for
  Linux (WSL) enabled, or see the PuTTY guide in the Windows folder.

## Running commands

Type a command and press Enter.  Try the following:

```bash
whoami     # display your username
pwd        # print working directory
date       # show the current date and time
echo "Hello, world!"  # print text to the screen
```

Commands may have **options** (flags) and **arguments**.  For example,
`ls -l /home` lists the contents of `/home` in long format.

## Getting help

Most UNIX commands provide help:

* `man <command>` – read the manual page for a command.  Use the
  arrow keys to scroll and **q** to quit.
* `<command> --help` – display a summary of options.

Autocompletion and history can speed up your workflow.  Press
**Tab** to autocomplete file names or commands, and use the arrow
keys to recall previous commands.

### Exercises

1. Print the current date, your username and your working directory on
   separate lines.
2. Use `man` to find the option that lists file sizes in a human‑readable
   format with `ls`.