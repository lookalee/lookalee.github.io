---
layout: single
title: "Git Basic Commands (2)"
tags: [git, github]
categories: git
---

`git init` : use locally for Git initialization. creates the *.git* file which will contain all future version management info.

`git add [file]` : after making changes, add [file] to staging level

`git add --all` : adds all modified files to staging level usnig a single line.

`git status`, `git diff` : checking file status (its a good habit to do this constantly)

`git commit -m "[commit description]"` : commit along with a simple commit message. Once this is done, we are done updating to a new version.

`git log` : check previous commit history (every time we commit, a 40-digit commit code is generated, which represents a 'snapshot' of the whole repository at the point when the commit was made). 

- Each commit history consists of a commit code, date, author, and commit message
- We can restore to a previous version of the repository using the 40-digit commit code , using the methods described in the 4th article of this git blog: https://lookalee.github.io/git/4-git-restore-prev-ver/. 

`git remote add origin [url]` : Connect local space to the remote space, using the name 'origin' (this step can be done in the beginning). for [url], you can use the one shown in github page's repository screen.

`git push origin main` : push changes to the main branch of remote repository. This "syncs" the local space with the remote space, meaning they will have identical contents.

**Misc**:
 `git config --global user.name="[username]"` : setting git username
 `git config --global user.email="[email]"` : setting git email
 `git --help` : show all git commands and descriptions

#### Important files worth mentioning:

- *README.md* : contains project description, manual, licenses, etc. 
  - serves as the "Main page" of the repository.
  - It's a very good habit to include this to every repository not only because it provides guidance to others, but also because it can serve as a future individual reference.
  - Possible inclusions to a README.md, depending on the type of project:
    1. Project Description (image / logo)
    2. Installation guide
    3. Code samples
    4. Method for setting development environment
    5. Method for others to contribute to project
    6. Log changes
    7. Credits
    8. Licenses (if open-source, possibly prevents others from getting credit using your work)
    9. Contacts
- *.git* : consists version management info. It is advised to not mess with this file. 
- *.gitignore* : add files here to ignore them (do NOT save. do NOT track)

