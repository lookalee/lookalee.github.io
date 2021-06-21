---
layout: single
title:  "1. Importance of using Git"
tags: [git, github, vcs]
categories: git
---

Git is a **VCS** (Version Control System).

**Why do we need to use Git?**

- Version Management: Allows us to keep track of changes we make to a project. 
  - Can keep backups of previous versions so we can return to it when needed.
  - By storing versions in a remote space, decreases local space usage.
  - In a team project, allows us to track who made changes to a certain file.

**Centralized vs Distributed** **Version Control System**

|                          CVCS                           |                             DVCS                             |
| :-----------------------------------------------------: | :----------------------------------------------------------: |
|                    Used in the past                     |                        Being used now                        |
| Needs internet access to work (works like Google Drive) | Can work locally by cloning to local space, and push/pull whenever desired |
|                                                         |          Keeps track of versions using 'snapshots'           |

![Screenshot-2021-06-21-at-10.30.17-PM](assets/images/Screenshot-2021-06-21-at-10.30.17-PM.png)

**Advantages of Git:**

1. Fast
2. Simple Structure
3. Supports non-linear development
4. Perfect distribution
5. Useful for large projects like Linux Kennels.

**Steps of using Git:**

1. Initialization & Repository
   - **Repository** is a collection of files of various versions of a project.
2. Add / Modify / Delete files
3. Select desired changes
4. Update status

**Version Control Syntax**: [A].[B].[C].
ex) 0.0.1, 1.1.0

- [A] : Major : A new version that is not compatible with the previous version.
- [B] : Minor : Addition of features
- [C] : Patch : Minor bug fixes 

