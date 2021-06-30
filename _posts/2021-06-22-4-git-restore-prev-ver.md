---
layout: single
title: "How to use 'git checkout' to restore previous version of git repository (4)"
tags: [git, github]
categories: git

---

> One of the main advantages of using Git is version management. Here is one way to restore a repository to its previous version.

The main function of `git checkout` command is to switch to another git branch. However, it can also be used to  overwrite the current directory with a specified snapshot from the commit history. 

### Steps to rollback to a previous Git commit using `git checkout` :

1. Using `cd` command, navigate to the directory of the repository that you wish to perform rollback.
2. either ***1.*** do `git log` to find the commit id that you wish to rollback to, or ***2.*** find the commit id on github's commit history. 
3. do `git checkout [commmit ID] .` 
   - IMPORTANT: do not leave out the trailing ' . ' after the commit ID when doing `git checkout`! 
4. do `git commit -m "[commit message]"`

