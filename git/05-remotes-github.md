# Remotes & GitHub

Collaborating with others usually involves pushing your local commits to
a remote host such as GitHub, GitLab or Bitbucket.  A **remote** is
simply another copy of the repository accessible over a network.

## Add a remote

After creating a repository on GitHub, copy the SSH or HTTPS URL.  Then
run:

```bash
git remote add origin git@github.com:your‑org/your‑repo.git
```

`origin` is the conventional name for the main remote.  You can view
configured remotes with:

```bash
git remote -v
```

## Push and pull

Push your local `main` branch to the remote and set it to track
`origin/main`:

```bash
git push -u origin main
```

The `-u` flag sets the upstream, so future `git push` and `git pull`
commands know which remote and branch to use.  To fetch updates from
others and integrate them:

```bash
git fetch               # fetch changes without merging
git pull --rebase       # fetch and rebase your commits on top
```

Using `--rebase` avoids unnecessary merge commits in your history.

## Pull requests (PRs)

On GitHub, collaboration often happens through **pull requests**.
Create a new branch for each feature or bug fix, push it to GitHub and
open a PR via the GitHub web interface or the GitHub CLI.  Reviewers
comment on your code, and once approved the branch is merged into
`main`.  Keeping branches short‑lived (small, focused changes) makes
reviews easier.

### Exercise

1. Create a remote repository on GitHub.
2. Add it as `origin` to your local repo.
3. Push your `main` branch and open a pull request for a feature branch.