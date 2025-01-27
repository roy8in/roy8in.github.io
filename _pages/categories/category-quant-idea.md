---
title: "Idea Note"
layout: archive
permalink: categories/quant-idea
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.quant-idea%}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
