# Essentials: create, commit and ignore

In this section you will create a new repository, add files, commit
changes and manage ignored files.

## Create a repository

```bash
mkdir demo && cd demo
git init           # initialise a new Git repository
```

Git creates a `.git` directory containing all metadata.  Nothing is
tracked until you add files.

## Add files and commit

Create a file and add it to the staging area:

```bash
echo "# Demo project" > README.md
git add README.md
```

Commit the change with a meaningful message:

```bash
git commit -m "init: add README"
```

Use `git status` to see the state of your working tree and `git log
--oneline` to view the commit history.

## Ignoring files

Create a `.gitignore` file to tell Git which files or directories
should not be tracked.  Common examples:

```
# .gitignore
.DS_Store       # macOS Finder metadata
*.log           # log files
node_modules/   # dependencies
venv/           # Python virtual environments
```

Add and commit the `.gitignore` file:

```bash
git add .gitignore
git commit -m "chore: add .gitignore"
```

## View changes

Use `git diff` to view unstaged changes and `git diff --staged`
to see changes in the staging area.  These commands help you review
what will be committed.

### Exercise

1. Initialise a new repository.
2. Create a Python file (`hello.py`), commit it, modify it and
   investigate the differences with `git diff`.
3. Add a `.gitignore` file to exclude compiled Python files (`*.pyc`).