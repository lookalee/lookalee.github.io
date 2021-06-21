---
layout: single
title: "3. How to use 'git fetch' and 'git reset' to overwrite local repository with remote version"
tags: [git, github, repository]
categories: git
---

> If changes have been made to the remote git repository, either by a team member or yourself (ex: modifying from github directly), you will not be able to push new local changes because the remote workspace is not synced with the local workspace. 
>
> In this case, a possible solution is to overwrite the local repository with the remote version using the `git fetch` command so that they are in sync. 

#### Using `git fetch` to force "git pull" from remote repository to overwite local files:

1. do `git fetch --all` 
2. do `git branch backup-main` to backup the current branch
3. do `git reset --hard origin/[branch name]` to finish overwriting local files with the remote version. 



- IMPORTANT NOTE: All local changes that have been made will be **lost** if `git fetch` is used. If needed, you can maintain the local commits by creating a new branch. This can be done using the following commands:
  - `git checkout main
    git branch [new branch name]
    git fetch --all`
  - Now, you can do `git reset --hard origin/[new branch name]` to overwite the local files while keeping the old version in the new branch. 
