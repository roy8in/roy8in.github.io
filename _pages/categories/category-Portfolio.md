---
layout: category
title: 'Portfolio'
permalink: categories/Portfolio
author_profile: true
sidebar_main: true

---

***

{% assign posts = site.categories['Portfolio'] | sort:"date" | reverse %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}