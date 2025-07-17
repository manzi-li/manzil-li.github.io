---
layout: page
permalink: /teaching/
title: teaching
description: Materials for courses you taught. Replace this text with your description.
nav: true
nav_order: 4
horizontal: false
---

For now, this page is assumed to be a static description of your courses. You can convert it to a collection similar to `_projects/` so that you can have a dedicated page for each course.

Organize your courses by years, topics, or universities, however you like!

<!--
This version uses direct HTML to display the cards, bypassing the include template to fix the display issue.
-->

<div class="projects">
{%- assign sorted_teaching = site.teaching | sort: "importance" -%}
<div class="row row-cols-1 row-cols-md-3">
{%- for course in sorted_teaching -%}
<div class="col">
<div class="card h-100">
{%- if course.img %}
<img src="{{ course.img | prepend: 'assets/img/' | relative_url }}" class="card-img-top" alt="{{ course.title }}">
{%- endif %}
<div class="card-body">
<h5 class="card-title">{{ course.title }}</h5>
<p class="card-text">{{ course.description }}</p>
</div>
</div>
</div>
{%- endfor -%}
</div>
</div>