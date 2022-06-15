---
title: "Web Development"
layout: archive
permalink: categories/webdev
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.["Web Development"] %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
