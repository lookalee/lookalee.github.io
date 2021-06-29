---
layout: single
title: "Fixing error: failed to push some refs to.. (6)"
tags: [git, github]
categories: git

---

If you haven't pushed to a repository for a while, the following error might appear after you run `git push` :

*error: failed to push some refs to '[repository link]'*.

The screenshot of the error is below:

![image-20210629201745822](/assets/images/image-20210629201745822.png)

One way to fix this is by running `git pull --rebase` or `git pull --rebase origin main` before doing `git push`.

pulling using --rebase will basically reapply the local changes on top of the remote changes. It is good practice to always rebase your local changes before pushing to the repository. 