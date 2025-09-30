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

A **pull request** (PR) is GitHub's mechanism for proposing changes to a
repository.  It's called a "pull request" because you're asking the
project maintainers to "pull" your changes into their codebase.  PRs
are essential for collaboration, code review, and maintaining code
quality.

### What is a pull request?

A pull request:
* Proposes changes from one branch to another (typically from a feature
  branch to `main`)
* Provides a space for discussion, code review, and feedback
* Shows a diff of all changes being proposed
* Can trigger automated tests and checks
* Creates a permanent record of why changes were made

### Creating a pull request

#### Step 1: Create and work on a feature branch

Start by creating a new branch for your changes:

```bash
git checkout -b feature/add-user-authentication
# Make your changes, add files, commit
git add .
git commit -m "feat: add user authentication system"
```

#### Step 2: Push your branch to GitHub

```bash
git push -u origin feature/add-user-authentication
```

#### Step 3: Open the pull request

**Via GitHub web interface:**
1. Navigate to your repository on GitHub
2. Click the "Compare & pull request" button (appears after pushing)
3. Or go to the "Pull requests" tab and click "New pull request"
4. Select your feature branch as the source and `main` as the target
5. Add a descriptive title and detailed description
6. Click "Create pull request"

**Via GitHub CLI:**
```bash
gh pr create --title "Add user authentication system" \
  --body "Implements login/logout functionality with JWT tokens"
```

### Writing good pull request descriptions

A good PR description should include:
* **What** changes you made
* **Why** you made them
* **How** to test the changes
* Any breaking changes or migration notes
* Screenshots for UI changes

Example:
```
## What
Adds user authentication system with login/logout functionality.

## Why
Users need to be able to create accounts and securely access their data.

## How to test
1. Run `npm test` to verify all tests pass
2. Start the dev server and navigate to /login
3. Try creating a new account and logging in

## Notes
- Uses JWT tokens for session management
- Passwords are hashed with bcrypt
- No breaking changes to existing API
```

### Pull request workflow

1. **Create** the PR with a clear title and description
2. **Request reviewers** – tag team members who should review
3. **Address feedback** – make changes based on review comments
4. **Update** the PR by pushing new commits to the same branch
5. **Merge** once approved (usually done by maintainers)

Common merge strategies:
* **Merge commit** – preserves branch history
* **Squash and merge** – combines all commits into one
* **Rebase and merge** – replays commits without a merge commit

Keeping branches short‑lived (small, focused changes) makes reviews
easier and reduces merge conflicts.

### Exercise

Contributing to open source projects is about identifying opportunities to improve the codebase, documentation, or user experience. When you approach a repository as a potential contributor, you're looking for gaps, errors, or enhancements that would benefit other users. This might be fixing a typo that confuses readers, adding a missing example that would clarify a concept, contributing a useful resource you've discovered, or improving unclear explanations. The key is to think like a user of the documentation: What confused you? What would have been helpful when you were learning? What resources did you find valuable that aren't mentioned? Start small with your first contributions—fixing typos, improving formatting, or adding simple examples are excellent ways to get comfortable with the contribution workflow before tackling larger changes.

#### Basic exercise (your own repository)
1. Create a remote repository on GitHub.
2. Add it as `origin` to your local repo.
3. Push your `main` branch to establish the remote connection.
4. Create a new feature branch: `git checkout -b feature/update-readme`
5. Make some changes (e.g., update the README file).
6. Commit and push the feature branch: `git push -u origin feature/update-readme`
7. Open a pull request via the GitHub web interface or CLI.
8. Practice writing a good PR description with what/why/how sections.

#### Hands-on exercise (contribute to this repository!)
Practice the full open source contribution workflow by contributing to this very repository:

1. **Fork this repository** on GitHub:
   - Go to https://github.com/[repository-url] (replace with actual URL)
   - Click the "Fork" button to create your own copy

2. **Clone your fork** locally:
   ```bash
   git clone git@github.com:YOUR-USERNAME/rcr-foundations.git
   cd rcr-foundations
   ```

3. **Create a feature branch**:
   ```bash
   git checkout -b add-my-contribution
   ```

4. **Make a meaningful contribution**:
   - Add a useful resource to one of the `resources.md` files
   - Fix a typo or improve clarity in any guide
   - Add a helpful tip or example to any section
   - Create a new file in the appropriate directory with additional information

5. **Commit your changes**:
   ```bash
   git add .
   git commit -m "docs: add [description of your contribution]"
   ```

6. **Push your branch**:
   ```bash
   git push -u origin add-my-contribution
   ```

7. **Create a pull request**:
   - Go to your fork on GitHub
   - Click "Compare & pull request"
   - Write a clear description of what you added and why
   - Submit the PR to the original repository

This exercise demonstrates the complete fork → clone → branch → PR workflow that's essential for contributing to open source projects. **Note**: Since this is a public repository, you cannot push directly to it - you must fork first, which is the standard open source contribution pattern.
