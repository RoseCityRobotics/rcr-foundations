# Navigation & files

Navigating the filesystem and manipulating files are core skills on any
UNIX system.

## Listing and changing directories

```bash
ls -lah         # list files in the current directory in long format
cd /path/to/dir # change into a directory
cd ~            # change to your home directory
cd ..           # move up one directory
```

Tip: `ls -a` shows hidden files (those starting with a dot), and
`ls -h` prints sizes in a human‑readable format.

## Creating, copying and moving files

```bash
touch notes.txt          # create an empty file
cp notes.txt notes.bak   # copy a file
mv notes.txt docs/       # move/rename a file or directory
mkdir -p project/src     # create nested directories
rm notes.bak             # remove a file (irreversible!)
```

The `rm` command permanently deletes files.  Double‑check the path
before pressing Enter.

## Redirection and pipes

UNIX allows you to connect commands together using **redirection** and
**pipes**.  This is one of the most powerful features of the shell.

```bash
echo "hello" > hello.txt  # write output to a file (overwrite)
cat hello.txt | wc -c     # count characters in a file using a pipe
grep -i "error" logfile.txt | less  # search case‑insensitive and page through results
```

* Redirection (`>`, `>>`, `<`) sends command output to a file or input
  from a file.
* Pipes (`|`) connect the output of one command to the input of another.

## Practice

1. Make a directory called `proj`, create a file inside it with three
   lines of text, and count the number of lines using `wc -l`.
2. Use `grep` to find a word in one of your system log files (e.g.,
   `/var/log/syslog` on Ubuntu) and pipe the output to `less`.