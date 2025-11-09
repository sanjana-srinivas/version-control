# Version Control System (VCS) — Git Setup and Commands

## Overview
Version control systems help developers track, manage, and collaborate on changes to codebases.

This document covers Git installation, configuration, and a clean separation of **Local** and **Remote** Git commands.

---

## 1. Installation

### Windows
1. Download Git from https://git-scm.com/downloads  
2. Run the installer and accept the defaults.  
3. Open **Git Bash** after installation.

### macOS
```bash
brew install git

2. Configuration

Configure your identity for commits:
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

View configuration:

git config --list

Edit global configuration in your default editor:

git config --global --edit


3. Repository Setup

Initialize a new repository:

git init
