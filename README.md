Version Control System (VCS) – Git Setup and Commands
Overview

Version Control Systems help developers track, manage, and collaborate on changes to codebases.
Git is the most widely used distributed version control system that enables efficient collaboration and code versioning.

This document covers Git installation, configuration, and a complete list of local and remote Git commands.

1. Installation
Windows

Download Git from https://git-scm.com/downloads
.

Run the installer and select default options.

Open Git Bash after installation.

macOS
brew install git

Linux (Ubuntu/Debian)
sudo apt update
sudo apt install git

2. Configuration

Once installed, configure your identity for commits:

git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

View Configuration
git config --list

Edit Configuration
git config --global --edit

3. Repository Setup
Initialize a New Repository
git init


Creates a hidden .git directory that tracks version history.

Clone an Existing Repository
git clone https://github.com/username/repo-name.git

4. Git Command Reference
A. Local Commands

Local commands operate within your local system or repository.

Command	Description
git init	Initializes a new local repository
git status	Displays the state of the working directory and staging area
git add <filename>	Stages specific file changes
git add .	Stages all modified and new files
git commit -m "message"	Saves staged changes with a descriptive message
git log	Displays the commit history
git diff	Shows file differences between working directory and index
git branch	Lists local branches
git branch <branch-name>	Creates a new branch
git checkout <branch-name>	Switches to another branch
git checkout -b <branch-name>	Creates and switches to a new branch
git merge <branch-name>	Merges another branch into the current branch
git stash	Temporarily saves uncommitted changes
git stash pop	Restores stashed changes
git rm <filename>	Removes a file from the working directory and staging area
git mv <old> <new>	Renames or moves a file
git reset <filename>	Unstages a staged file
git reset --soft HEAD~1	Undo the last commit but keep changes staged
git checkout -- <filename>	Discards local modifications
B. Remote Commands

Remote commands interact with repositories hosted on platforms like GitHub, GitLab, or Bitbucket.

Command	Description
git remote add origin <url>	Adds a remote repository connection
git remote -v	Displays all remote repository URLs
git remote remove origin	Removes an existing remote connection
git fetch	Retrieves latest changes from remote but doesn’t merge
git pull origin main	Fetches and merges changes from the remote main branch
git push origin main	Uploads local commits to the remote main branch
git push -u origin main	Pushes and sets upstream tracking for the main branch
git push origin --delete <branch>	Deletes a branch from the remote repository
git clone <url>	Creates a copy of a remote repository locally
5. Configuration Commands Summary
Command	Description
git config --list	Lists all current Git configurations
git config user.name	Shows configured username
git config user.email	Shows configured email
git config --global user.name "Name"	Sets username globally
git config --global user.email "email"	Sets email globally
git config --system core.editor "editor"	Sets default text editor
git config --global color.ui auto	Enables color in Git output
git config --global alias.st status	Creates an alias (e.g., git st = git status)
6. Basic Git Workflow
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

7. Common Use Cases
Undo Last Commit (keep changes)
git reset --soft HEAD~1

Undo Changes in Working Directory
git checkout -- <filename>

Check Differences Between Commits
git diff commit1 commit2

Revert a Specific Commit
git revert <commit-id>

8. Quick Reference Table
Task	Command
Check repository status	git status
Stage changes	git add .
Commit staged changes	git commit -m "message"
View history	git log
Create new branch	git checkout -b <branch>
Merge branches	git merge <branch>
Push to remote	git push origin main
Pull from remote	git pull origin main
9. Best Practices

Always pull before pushing changes.

Use meaningful commit messages.

Create a new branch for each feature or fix.

Keep the main branch stable.

Use .gitignore to exclude unnecessary files.

Regularly review commit history and branches.

10. Conclusion

This README provides a comprehensive reference for setting up Git, configuring user details, and using both local and remote commands effectively.
Following these practices ensures clean version control, better collaboration, and maintainable code history.