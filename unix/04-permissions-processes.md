# Permissions & processes

Understanding file permissions and process management allows you to
secure your system and troubleshoot applications.

## Permissions

Every file and directory has **owner**, **group** and **other**
permissions for reading (`r`), writing (`w`) and executing (`x`).
List permissions with `ls -l`:

```bash
ls -l script.sh
```

To make a script executable:

```bash
chmod +x script.sh
```

To change ownership of a file (requires `sudo` unless you are the
owner):

```bash
sudo chown $USER:$USER file.txt
```

Be careful when using `chmod` and `chown` on system files; incorrect
permissions can break software.

## Processes

Use `ps` to list running processes.  The following command shows all
processes in a format that fits on one screen:

```bash
ps aux | head
```

For a real‑time view, use `top` or `htop` (install with
`sudo apt install htop` on Ubuntu).  Press **q** to quit.

To terminate a process, first find its PID (process ID) with `ps` or
`top`, then run:

```bash
kill <pid>
```

If the process does not terminate, you can send a stronger signal with
`kill -9 <pid>` but this should be a last resort.

## Exercise

1. Write a simple script (`sleep.sh`) that sleeps for 30 seconds.
   Make it executable and run it in the background (`./sleep.sh &`).
2. Use `ps` to find the PID and terminate the process using `kill`.