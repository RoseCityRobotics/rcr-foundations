# Shell scripting basics

Shell scripts allow you to automate tasks and combine commands into
reusable programs.  Bash is the most common shell on Linux and macOS.

## Creating a script

1. Create a file called `hello.sh` using your text editor.
2. Add the following content:

```bash
#!/usr/bin/env bash
# Exit immediately on error, treat unset variables as errors, and ensure
# pipelines fail on the first error.
set -euo pipefail

name=${1:-world}
echo "Hello, $name!"
```

3. Save the file and make it executable:

```bash
chmod +x hello.sh
```

4. Run the script:

```bash
./hello.sh           # prints "Hello, world!"
./hello.sh RCR       # prints "Hello, RCR!"
```

## Key concepts

* **Shebang (`#!`):** Specifies the interpreter.  Using `/usr/bin/env`
  makes your script portable across systems.
* **`set -euo pipefail`:** Recommended for robust scripts.
* **Arguments (`$1`, `$2`, …):** Allow users to pass parameters.  Use
  `${var:-default}` to set a default.
* **Variables:** Always quote variables (`"$var"`) to prevent word
  splitting.

## Exercise

Write a script named `backup.sh` that takes a directory path as an
argument and archives it into a time‑stamped tar file (e.g.,
`backup-2025-09-29.tar.gz`).  Use `tar -czf` and `$()` to capture the
current date.  Remember to make the script executable.