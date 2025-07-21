---
layout: page
permalink: /teaching/
title: Teaching
description:
nav: true
nav_order: 4
horizontal: false
---

<style>
.card-link, .card-link:hover {
color: inherit;
text-decoration: none;
}
</style>

<div class="projects">
{%- assign sorted_teaching = site.teaching | sort: "importance" -%}
<div class="row row-cols-1 row-cols-md-3">
{%- for course in sorted_teaching -%}
<div class="col mb-4">
<a href="{{ course.url | relative_url }}" class="card-link">
<div class="card h-100">
{%- if course.img %}
<img src="{{ course.img | relative_url }}" class="card-img-top" alt="{{ course.title }}">
{%- endif %}
<div class="card-body">
<h5 class="card-title">{{ course.title }}</h5>
<p class="card-text">{{ course.description }}</p>
</div>
</div>
</a>
</div>
{%- endfor -%}
</div>
</div>