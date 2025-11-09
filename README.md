# Version Control System (VCS) — Git Setup and Commands

## Overview
Version Control Systems help developers track, manage, and collaborate on code changes.  
**Git** is the most widely used distributed VCS that enables efficient collaboration and code versioning.

This document explains Git installation, configuration, and provides a clear distinction between **Local** and **Remote** Git commands.

---

## 1. Installation

### Windows
1. Download Git from [https://git-scm.com/downloads](https://git-scm.com/downloads)  
2. Run the installer and accept the defaults  
3. Open **Git Bash** after installation

### macOS
```bash
brew install git


Linux (Ubuntu / Debian)
sudo apt update
sudo apt install git

2. Configuration

Configure your name and email (these appear in your commits):

git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"


View all configuration details:

git config --list


Edit your global configuration file:

git config --global --edit

3. Repository Setup
Initialize a new repository
git init


Creates a hidden .git directory that stores version history.

Clone an existing repository
git clone https://github.com/username/repo-name.git

4. Git Command Reference
A. Local Commands

Local commands operate within your local repository.

Command	Description
git init	Initialize a new local repository
git status	Show working directory and staging area status
git add <filename>	Stage specific file changes
git add .	Stage all modified and new files
git commit -m "message"	Commit staged changes with a message
git log	Display commit history
git diff	Show unstaged changes
git branch	List local branches
git branch <branch-name>	Create a new branch
git checkout <branch-name>	Switch to another branch
git checkout -b <branch-name>	Create and switch to a new branch
git merge <branch-name>	Merge a branch into the current branch
git stash	Temporarily save uncommitted changes
git stash pop	Restore stashed changes
git rm <filename>	Remove file from repo and working directory
git mv <old> <new>	Rename or move a file
git reset <filename>	Unstage a staged file
git reset --soft HEAD~1	Undo the last commit but keep changes staged
git checkout -- <filename>	Discard local modifications in a file
B. Remote Commands

Remote commands interact with repositories hosted on platforms like GitHub, GitLab, or Bitbucket.

Command	Description
git remote add origin <url>	Add a remote repository connection
git remote -v	Display all remote repository URLs
git remote remove origin	Remove an existing remote connection
git fetch	Retrieve latest changes from remote (no merge)
git pull origin main	Fetch and merge latest changes from remote main branch
git push origin main	Push local commits to remote main branch
git push -u origin main	Push and set upstream for main branch
git push origin --delete <branch>	Delete a remote branch
git clone <url>	Clone a remote repository locally
5. Basic Git Workflow

A typical sequence for setting up and pushing your first commit:

# Step 1: Initialize repository
git init

# Step 2: Add remote origin
git remote add origin https://github.com/username/repo-name.git

# Step 3: Stage all files
git add .

# Step 4: Commit changes
git commit -m "Initial commit"

# Step 5: Push to main branch
git push -u origin main

6. Common Use Cases
Undo last commit but keep changes staged
git reset --soft HEAD~1

Discard changes in a specific file
git checkout -- <filename>

Compare differences between two commits
git diff <commit1> <commit2>

Revert a specific commit
git revert <commit-id>

7. Quick Reference Table
Task	Command
Check repository status	git status
Stage changes	git add .
Commit changes	git commit -m "message"
View commit history	git log
Create new branch	git checkout -b <branch>
Merge a branch	git merge <branch>
Push changes	git push origin main
Pull latest changes	git pull origin main
8. Best Practices

Always pull before pushing to avoid conflicts

Write clear, descriptive commit messages

Use feature branches for new work

Keep the main branch stable

Add a .gitignore file for unnecessary or sensitive files

Review changes before committing (git diff)

9. Configuration Reference
Command	Description
git config --list	Show all current configuration values
git config user.name	Show configured username
git config user.email	Show configured email
git config --global user.name "Name"	Set global username
git config --global user.email "Email"	Set global email
git config --system core.editor "editor"	Set default text editor
git config --global color.ui auto	Enable colored output
git config --global alias.st status	Create alias (example: git st for git status)
10. Conclusion

This README provides a complete reference for Git setup, configuration, and essential commands.
Following these steps ensures organized version control, smooth collaboration, and efficient workflow management.