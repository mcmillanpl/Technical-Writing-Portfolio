---
layout: page
title: Git Command Quick Reference
---

# Git Command Quick Reference

This document provides a foundational reference for version control workflows, covering directory navigation, Git configuration, and the standard remote repository lifecycle.

## Navigation
Commands used to navigate and inspect directories on your local machine.

| Command | Description |
| ----------- | ----------- |
| `cd ..` | Moves up one directory level. |
| `cd <directory_name>` | Enters the specified directory. |
| `cd -` | Returns to the previous working directory. |
| `pwd` | Prints the current working directory path. |
| `ls` | Lists files and folders in the current directory. |
| `ls -a` | Lists all files, including hidden files (e.g., `.git`). |
| `ls -l` | Lists files in **long format** (showing permissions, size, and owner). |

## File & Directory Management
Commands for managing the physical structure of your project files.

| Command | Description |
| ----------- | ----------- |
| `mkdir <directory_name>` | Creates a new empty folder. |
| `touch <filename.extension>` | Creates a new empty file. |
| `git mv <old_name> <new_name>` | Renames or moves a file and stages the change in Git. |

## Configuration
Setting up your identity within the Git environment.

| Command | Description |
| ----------- | ----------- |
| `git config --global user.name "<name>"` | Sets your commit username globally. |
| `git config --global user.email "<email>"` | Sets your commit email address globally. |

## The Git Workflow
These commands move data between your working directory, the staging area, and the remote repository.



| Command | Description |
| ----------- | ----------- |
| `git init` | Initializes a new Git repository in the current folder. |
| `git clone <url>` | Downloads an existing repository from a remote source. |
| `git status` | Shows which files are staged, unstaged, or untracked. |
| `git add .` | Stages all changes in the current directory for the next commit. |
| `git commit -m "<message>"` | Records your staged changes with a descriptive message. |
| `git log` | Displays a chronological history of commits. |
| `git push origin <branch>` | Uploads local commits to the remote repository. |
| `git pull` | Fetches and merges changes from the remote to your local copy. |

## Branching & Collaboration
Commands for managing parallel versions of a project.

| Command | Description |
| ----------- | ----------- |
| `git branch -a` | Lists all local and remote branches. |
| `git switch <branch>` | Switches to the specified branch. |
| `git switch -c <branch>` | Creates a new branch and switches to it immediately. |
| `git branch -d <branch>` | Deletes a local branch (use `-D` to force delete). |
| `git remote add upstream <url>` | Maps a forked repository to the original "upstream" source. |
| `git fetch upstream` | Retrieves updates from the original repository without merging them. |

---

### Documentation Standards
* **CLI Syntax**: Required parameters are enclosed in `<brackets>`.
* **Accuracy**: Verified against Git version 2.23+ (utilizing `switch` over `checkout` for branch management).