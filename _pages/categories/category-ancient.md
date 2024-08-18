---
title: "고대 세계 (~500)"
layout: archive
permalink: categories/ancient
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.ancient %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}