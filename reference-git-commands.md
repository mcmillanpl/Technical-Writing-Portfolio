# Git commands

## Overview
This reference document outlines a basic reference page for beginner Git users, such as navigating and creating directories, configuring Git, and setting up a remote repository. 

## Navigation
The following commands are used to navigate directories/files on your local computer. 

| Command | Description |
| ----------- | ----------- |
| `cd ..` | Takes you to the directory above the one you're currently in. |
| `cd <directory_name>` | Enter and open a directory. |
| `cd -` | Returns you to the previous directory. |
| `pwd` | Displays your current file path. |
|`pwd -p` | Displays the full current file path. |
| `ls` | Lists all files in a directory. |
| `ls -a` | Lists and files and hidden files in a directory. |
| `ls -l` | Lists all directories in a directory. |

## Create/rename files and directories
The following commands are used to create new files/directories, as well as rename them.

| Command | Description |
| ----------- | ----------- |
| `git mv <old_filename> <new_filename>` | Renames a file. |
|  `mkdir <directory_name>` | Creates an empty folder. |
| `touch <filename.extension>` | Creates an empty file. |

## Configure Git
The following commans are used to configure a [Git environment](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup) for your repositories on your local computer. 

| Command | Description |
| ----------- | ----------- |
| `git config --global user.name "<username>"` | Sets Git username. |
|  `git config --global user.email "<email>"` | Sets Git email address. |

## Perform Git workflow actions
The following commands can be used to perform actions as part of the [Git workflow](https://uidaholib.github.io/get-git/3workflow.html).

| Command | Description |
| ----------- | ----------- |
| `git clone` | Clones a repository to your local computer, using either an HTTPS or SSH URL. |
| `git status` | Displays the current state of your repository and staging area. |
| `git log` | Lists all recent activities. |
| `git add .` | Stages your files after applying and saving changes. |
| `git commit -m "<message>"` | Records the changes made to a file. Use this command after staging the file (`add .`). Within the quotation marks, you can enter a message that describes the changes. |
| `git push` | Pushes changes made in the local repository to the remote (GitHub.com) repository. |
| `git push origin main` | Pushes changes from a different branch to the main branch. |
| `git pull` | Updates the local repository by pulling and merging updates from the remote repository. |
| `git fetch` | Displays changes made in the remote repository. It does not merge any changes with the local repository. |
| `git remote -v` | Lists the URL of your remote repository in your terminal. The word _origin_ will appear at the start of your remote connection or remote repository's URL. Origin is the default and convention for the remote repository. |
| `git init <directory>` | Creates a new Git repository or converts an existing local and unversioned directory into a Git repository. To convert a directory into a Git repository, open the directory using `cd` and enter `git init`. |
| `git branch --all` | Lists all the branches within your repository. |
| `git checkout <branch_name>` | Switches you to a different branch. |
| `git checkout -b <branch-name>` | Creates a new branch and switches to it at the same time. |
| `git switch <branch_name>` | Switches you to a different branch. (Git v2.23+) |
| `git switch -c <branch-name>` | Creates a new branch and switches to it at the same time. (Git v2.23+) |
| `git branch -d -r origin/feature/<branch>` | Deletes a local branch. |
| `git fetch add upstream <link>` | Adds the upstream to your forked repository, allowing you to push changes to the original repository. When adding the upstream, make sure to use the HTTPS or SSH link. |
| `git fetch upstream main` | Pulls any updates from the main branch of the forked repository to your local copy. |
