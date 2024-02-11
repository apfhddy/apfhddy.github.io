---
title: "Java > Spring Boot"
layout: single
permalink: /java/springBoot
author_profile: true
sidebar:
    nav: "sidebar-category"
---

{% assign posts = site.categories.java %}
{% for post in posts %}
    {% if post.categories.size > 1 and post.categories[1] == "spring boot" %}
        {% include archive-single.html type=page.entries_layout %}
    {% endif %}
{% endfor %}