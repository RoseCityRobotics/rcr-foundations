# Branching & merging

Branches allow you to work on new features or experiments without
affecting the `main` branch.  Merging combines changes from one branch
into another.

## Overview: Branching, cloning, and forking

Understanding the differences between these three concepts is crucial
for effective Git collaboration:

### Branching
**Branching** creates a new line of development within the same
repository.  All branches share the same history up to the point where
they diverged.

* **Use case**: Working on features, bug fixes, or experiments
* **Scope**: Local to your repository (though branches can be pushed to remotes)
* **Collaboration**: Team members work on different branches of the same repo
* **Example**: `git checkout -b feature/user-login`

### Cloning
**Cloning** creates a complete copy of an existing repository on your
local machine.  You get all branches, commits, and history.

* **Use case**: Getting a local copy of a remote repository to work on
* **Scope**: Creates a new local repository linked to the original remote
* **Collaboration**: Standard way to start contributing to a project
* **Example**: `git clone git@github.com:user/project.git`

### Forking
**Forking** creates a complete copy of a repository under your own
GitHub account.  It's GitHub's way of copying repositories between
different users or organizations.

* **Use case**: Contributing to projects you don't have write access to
* **Scope**: Creates a new repository on GitHub that you own
* **Collaboration**: Fork → clone → branch → pull request workflow
* **Example**: Click "Fork" button on GitHub, then clone your fork

### When to use each

| Scenario | Method | Workflow |
|----------|--------|----------|
| Team member on shared project | **Clone + Branch** | Clone repo → create feature branch → push → PR |
| Contributing to open source | **Fork + Clone + Branch** | Fork on GitHub → clone your fork → branch → PR |
| Experimenting locally | **Branch** | Create experimental branch in existing repo |
| Starting fresh with existing code | **Fork** or **Clone** | Depends on whether you need your own copy |

The typical open source contribution workflow combines all three:
1. **Fork** the original repository on GitHub
2. **Clone** your fork to your local machine
3. **Branch** for your specific changes
4. Push your branch and create a pull request

## Create and switch branches

```bash
git checkout -b feature/hello   # create and switch to a new branch
```

The `git checkout -b` command creates a new branch and checks it out.
Alternatively you can use `git switch -c feature/hello` if you have
Git 2.23 or later.

Make changes on your branch:

```bash
echo "Hello from feature" >> README.md
git add README.md
git commit -m "feat: say hello from feature branch"
```

## Merge into main

Switch back to `main` and merge:

```bash
git checkout main
git merge feature/hello
```

If there are no conflicting changes, Git performs a **fast‑forward
merge** and moves the `main` pointer to the feature branch’s tip.

### Resolving conflicts

Conflicts occur when the same lines were modified in both branches.
During a merge, Git stops and asks you to resolve conflicts manually.
Conflicted files contain markers like `<<<<<<<`, `=======` and
`>>>>>>>`.  Edit the file to keep the desired changes, then:

```bash
git add conflicted-file
git commit    # finishes the merge
```

You can always abort a merge with `git merge --abort` if needed.

## Undoing changes

Git provides several ways to undo:

* `git restore <file>` – Discard unstaged changes to a file.
* `git reset --soft HEAD~1` – Undo the last commit but keep your
  changes staged for a new commit.
* `git revert <commit>` – Create a new commit that undoes the changes
  introduced by a specific commit.

Understanding the differences between these commands helps you recover
from mistakes safely.

## Learn more

For hands-on practice with branching and merging concepts:
* [Learn Git Branching](https://learngitbranching.js.org/) – Interactive tool that visualizes branches and merges as you practice Git commands
