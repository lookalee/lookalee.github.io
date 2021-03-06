---
layout: single
title: "How to use 'git fetch' and 'git reset' to overwrite local repository with remote version (3)"
tags: [git, github, repository]
categories: git
toc: yes
---

> If changes have been made to the remote git repository, either by a team member or yourself (ex: modifying from github directly), you will not be able to push new local changes because the remote workspace is not synced with the local workspace. 
>
> In this case, a possible solution is to overwrite the local repository with the remote version using the `git fetch` command so that they are in sync. 

### Using `git fetch` to force "git pull" from remote repository to overwite local files:

1. do `git fetch --all` 
2. do `git branch backup-main` to backup the current branch
3. do `git reset --hard origin/[branch name]` to finish overwriting local files with the remote version. 



- IMPORTANT NOTE: All local changes that have been made will be **lost** if `git fetch` is used. If needed, you can maintain the local commits by creating a new branch. This can be done using the following commands:

  1. `git checkout main`

  2. `git branch [new branch name]`

  3. `git fetch --all`

  4. Now, you can do `git reset --hard origin/[new branch name]` to overwite the local files while keeping the old version in the new branch. 
