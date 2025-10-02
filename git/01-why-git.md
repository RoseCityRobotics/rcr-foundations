# Why Git

Version control systems keep track of changes to files over time.  They
allow multiple people to collaborate on a codebase without overwriting
each other’s work and provide a safety net when mistakes are made.

Git is the most widely used version control system today.  Some
advantages of Git include:

* **Local repositories:** You can commit and branch without a network
  connection; only pushes and pulls require remote access.
* **Branching model:** Lightweight branches make it easy to
  experiment without affecting the `main` branch.  You can merge or
  discard changes as needed.
* **Distributed collaboration:** Every clone of a repository is a full
  copy of the history.  There is no single point of failure.
* **Community and tooling:** Git has an enormous ecosystem of
  integrations (GitHub, GitLab, Bitbucket), graphical clients and
  extensions.

### Terminology

* **Repository (repo):** A directory containing your project’s files
  along with a hidden `.git` folder that stores its history.
* **Commit:** A snapshot of your files at a point in time along with a
  message describing the change.
* **Branch:** A movable pointer to a series of commits.  The default
  branch is usually called `main` or `master`.
* **Merge:** Combining changes from one branch into another.
* **Remote:** A separate copy of your repository hosted on another
  machine (e.g., GitHub).  `origin` is the default remote name.

Git might seem intimidating at first, but with practice it becomes a
powerful tool for managing projects of any size.

## Learn more

For visual learners, these short videos from the Git team provide excellent introductions:
* [What is Version Control?](https://git-scm.com/videos) (5:59) – Explains the fundamental concepts
* [What is Git?](https://git-scm.com/videos) (8:15) – Introduction to Git specifically
