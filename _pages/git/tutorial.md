---
title: "git > tutorial"
layout: single
permalink: /git/tutorial
author_profile: true
sidebar:
    nav: "sidebar-category"
---

{% assign posts = site.categories.git %}
{% for post in posts %}
    {% if post.categories.size > 1 and post.categories[1] == "tutorial" %}
        {% include archive-single.html type=page.entries_layout %}
    {% endif %}
{% endfor %}