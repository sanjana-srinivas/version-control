# Version Control System (VCS) — Git Setup and Commands

## Overview

Version Control Systems help developers track, manage, and collaborate on code changes.
**Git** is the most widely used distributed VCS that enables efficient collaboration, branching, and history tracking.

This README covers Git installation, configuration, and important local and remote commands, plus workflows and best practices.

---

## 1. Installation

### Windows

1. Download Git from [https://git-scm.com/downloads](https://git-scm.com/downloads)
2. Run the installer and accept default options
3. Open **Git Bash** after installation

### macOS

```bash
brew install git
```

### Linux (Ubuntu / Debian)

```bash
sudo apt update
sudo apt install git
```

---

## 2. Configuration

After installation, configure your username and email (these appear in commits):

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

### View Configuration

```bash
git config --list
```

### Edit Global Configuration

```bash
git config --global --edit
```

---

## 3. Repository Setup

### Initialize a New Repository

```bash
git init
```

Creates a hidden `.git` folder that tracks version history.

### Clone an Existing Repository

```bash
git clone https://github.com/username/repo-name.git
```

---

## 4. Git Command Reference

### A. Local Commands

Local commands operate within your local repository.

| Command                         | Description                                             |
| ------------------------------- | ------------------------------------------------------- |
| `git init`                      | Initialize a new local repository                       |
| `git status`                    | Show working directory and staging area status          |
| `git add <filename>`            | Stage specific file changes                             |
| `git add .`                     | Stage all modified and new files                        |
| `git commit -m "message"`       | Commit staged changes with a message                    |
| `git log`                       | Display commit history                                  |
| `git diff`                      | Show unstaged or staged changes                         |
| `git branch`                    | List local branches                                     |
| `git branch <branch-name>`      | Create a new branch                                     |
| `git checkout <branch-name>`    | Switch to another branch                                |
| `git checkout -b <branch-name>` | Create and switch to a new branch                       |
| `git merge <branch-name>`       | Merge a branch into the current branch                  |
| `git stash`                     | Temporarily save uncommitted changes                    |
| `git stash pop`                 | Restore stashed changes                                 |
| `git rm <filename>`             | Remove a file from the repository and working directory |
| `git mv <old> <new>`            | Rename or move a file                                   |
| `git reset <filename>`          | Unstage a staged file                                   |
| `git reset --soft HEAD~1`       | Undo the last commit but keep changes staged            |
| `git reset --hard HEAD~1`       | Undo the last commit and discard changes                |
| `git checkout -- <filename>`    | Discard local modifications in a file                   |

---

### B. Remote Commands

Remote commands interact with repositories hosted on GitHub, GitLab, Bitbucket, etc.

| Command                             | Description                                 |
| ----------------------------------- | ------------------------------------------- |
| `git remote add origin <url>`       | Add a remote repository named `origin`      |
| `git remote -v`                     | Display configured remote repository URLs   |
| `git remote remove origin`          | Remove an existing remote                   |
| `git fetch`                         | Fetch latest changes from remote (no merge) |
| `git pull origin main`              | Fetch and merge the remote `main` branch    |
| `git push origin main`              | Push local `main` to remote                 |
| `git push -u origin main`           | Push and set upstream tracking for `main`   |
| `git push origin --delete <branch>` | Delete a remote branch                      |
| `git clone <url>`                   | Clone a remote repository locally           |

---

## 5. Basic Git Workflow

Typical steps to initialize, commit, and push:

```bash
# Initialize repository
git init

# Add remote origin
git remote add origin https://github.com/username/repo-name.git

# Stage all files
git add .

# Commit
git commit -m "Initial commit"

# Push to main (set upstream)
git push -u origin main
```

---

## 6. Branching and Merging

Create a new branch:

```bash
git branch feature-xyz
```

Create and switch in one step:

```bash
git checkout -b feature-xyz
```

Switch to an existing branch:

```bash
git checkout feature-xyz
```

Merge branch into `main`:

```bash
git checkout main
git merge feature-xyz
```

Delete a local branch:

```bash
git branch -d feature-xyz
```

Delete a remote branch:

```bash
git push origin --delete feature-xyz
```

---

## 7. Undoing Changes

| Action                                 | Command                      |
| -------------------------------------- | ---------------------------- |
| Unstage a file                         | `git reset <filename>`       |
| Undo last commit (keep changes staged) | `git reset --soft HEAD~1`    |
| Undo last commit (discard changes)     | `git reset --hard HEAD~1`    |
| Restore a file from last commit        | `git checkout -- <filename>` |
| Remove file and untrack it             | `git rm <filename>`          |

---

## 8. Common Use Cases

Undo last commit but keep changes staged:

```bash
git reset --soft HEAD~1
```

Discard changes in a file:

```bash
git checkout -- <filename>
```

Compare two commits:

```bash
git diff <commit1> <commit2>
```

Revert a commit (creates a new commit that undoes the specified commit):

```bash
git revert <commit-id>
```

Temporarily save changes:

```bash
git stash
git stash list
git stash pop
```

---

## 9. Quick Reference Table

| Task              | Command                    |
| ----------------- | -------------------------- |
| Check status      | `git status`               |
| Stage all changes | `git add .`                |
| Commit            | `git commit -m "message"`  |
| View history      | `git log`                  |
| Create branch     | `git checkout -b <branch>` |
| Merge branch      | `git merge <branch>`       |
| Push to remote    | `git push origin main`     |
| Pull from remote  | `git pull origin main`     |

---

## 10. Sample .gitignore

```
# Byte-compiled / cache files
__pycache__/
*.py[cod]

# Environment files
.env

# Logs
*.log

# OS files
.DS_Store
Thumbs.db

# Node modules
node_modules/
```

---

## 11. Troubleshooting

* **Repeated username/password prompts**: use SSH or enable credential caching (`git config --global credential.helper cache`), or use a credential manager.
* **Merge conflicts**: resolve conflicts in files, then `git add` and `git commit`.
* **Recover deleted branch**: check `git reflog` and `git checkout -b <branch> <commit>` to recover.
* **File unexpectedly ignored**: check `.gitignore` and global gitignore (`git config --get core.excludesfile`).

---

## 12. Best Practices

* Pull before you push (`git pull`) to minimize conflicts.
* Use small, frequent commits with clear messages.
* Use feature branches for work; keep `main` stable.
* Use a `.gitignore` to avoid committing secrets or build artifacts.
* Review diffs (`git diff`) before committing.
* Protect main branches with branch protection rules on remote platforms.

---

## 13. Summary Commands (At a Glance)

```bash
# Initialize repo
git init

# Add remote
git remote add origin <url>

# Stage and commit
git add .
git commit -m "message"

# Push
git push -u origin main

# Branch and switch
git checkout -b new-feature

# Merge and delete branch
git checkout main
git merge new-feature
git branch -d new-feature
```

---

## 14. Conclusion

This README provides a complete, practical reference for installing, configuring, and using Git.
Use it as your day-to-day cheat sheet for local and remote Git tasks.
