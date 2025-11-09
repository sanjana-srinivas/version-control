# Version Control System (VCS) — Git Setup and Commands

## Overview
Version Control Systems help developers track, manage, and collaborate on code changes.  
**Git** is the most widely used distributed VCS that enables efficient collaboration, branching, and history tracking.

This README covers Git installation, configuration, and all major **local** and **remote** commands, along with best practices.

---

## 1. Installation

### Windows
1. Download Git from [https://git-scm.com/downloads](https://git-scm.com/downloads)  
2. Run the installer and accept default options  
3. Open **Git Bash** after installation

### macOS
```bash
brew install git

Linux (Ubuntu / Debian)

sudo apt update
sudo apt install git


2. Configuration

After installation, configure your username and email (this information appears in commits):

git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"


View Configuration

git config --list

Edit Configuration

git config --global --edit
