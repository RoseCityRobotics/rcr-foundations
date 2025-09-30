# Branching & merging

Branches allow you to work on new features or experiments without
affecting the `main` branch.  Merging combines changes from one branch
into another.

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