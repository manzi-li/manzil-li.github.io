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


<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
<!-- Display categorized teaching -->
{% for category in page.display_categories %}
<a id="{{ category }}" href=".#{{ category }}">
<h2 class="category">{{ category }}</h2>
</a>
{% assign categorized_teaching = site.teaching | where: "category", category %}
{% assign sorted_teaching = categorized_teaching | sort: "importance" %}
<!-- Generate cards for each course -->
{% if page.horizontal %}
<div class="container">
<div class="row row-cols-1 row-cols-md-2">
{% for course in sorted_teaching %}
{% include projects_horizontal.liquid project=course %}
{% endfor %}
</div>
</div>
{% else %}
<div class="row row-cols-1 row-cols-md-3">
{% for course in sorted_teaching %}
{% include projects.liquid project=course %}
{% endfor %}
</div>
{% endif %}
{% endfor %}

{% else %}

<!-- Display all teaching without categories -->

{% assign sorted_teaching = site.teaching | sort: "importance" %}

<!-- Generate cards for each course -->

{% if page.horizontal %}

<div class="container">
<div class="row row-cols-1 row-cols-md-2">
{% for course in sorted_teaching %}
{% include projects_horizontal.liquid project=course %}
{% endfor %}
</div>
</div>
{% else %}
<div class="row row-cols-1 row-cols-md-3">
{% for course in sorted_teaching %}
{% include projects.liquid project=course %}
{% endfor %}
</div>
{% endif %}
{% endif %}
</div>