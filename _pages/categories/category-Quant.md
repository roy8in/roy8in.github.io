---
layout: category
title: 'Quant'
permalink: categories/Quant
author_profile: true
sidebar_main: true

---

***

{% assign posts = site.categories.['Quant'] | sort:"date" | reverse %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}