---
title: "중세 시대 (500~1500)"
layout: archive
permalink: categories/medieval
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.medieval %}
{% for post in posts %} 
  {% include archive-single.html type=page.entries_layout %} 
{% endfor %}