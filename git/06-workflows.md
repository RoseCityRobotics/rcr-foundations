# Workflows

While Git can be used in many ways, adopting a consistent workflow
helps teams collaborate smoothly.  Here are some recommended practices:

## Use feature branches

Create a new branch for each unit of work (feature, bug fix, docs
update).  Keep branches small and focused; this makes it easier to
review changes and reduces merge conflicts.

## Write good commit messages

* Summarise the change in the first line (imperative mood, 50
  characters or less), followed by a blank line and an optional
  explanation.
* Follow the [Conventional Commits](https://www.conventionalcommits.org/)
  specification: prefixes like `feat:`, `fix:`, `docs:`, `refactor:`.

## Rebase and merge

Before merging your branch, update it with the latest changes from
`main`:

```bash
git fetch origin
git rebase origin/main
```

Fix any conflicts, test your code, then push.  When the PR is ready,
squash‑merge or rebase‑merge it to produce a clean history.

## Code review

Use pull requests to share changes with your team.  Provide context in
the PR description and tag reviewers.  During review:

* Ask clarifying questions and suggest improvements.
* Focus on design, readability and test coverage.
* Be respectful and constructive.

Following these practices helps maintain a high‑quality codebase and a
healthy team culture.