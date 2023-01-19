---
layout: single
title: "Web Application Planning Process"
tags: [web]
categories: web
toc: yes

---

### Web Application Planning Process

General planning steps of an application:

1. Come up with idea 
2. Create a sketch
3. Plan data models
4. Plan endpoints (API, backend)
   - User related APIs (/api/users/…)
     - ex) Retrieving list of all users, Create new user, Login user, etc
   - Place related APIs (/api/places/…)
     - ex) Retrieve all place for a given uid, Update place by pid, Delete place by pid, etc
5. Plan pages (SPA, frontend)
   - / : List of users
   - /:uid/places : List of places for user
   - /authenticate : Signup + Login Forms (only un-authenticated)
   - /places/new : New place form (only authenticated)
   - /places/:pid : Update place form (only authenticated)