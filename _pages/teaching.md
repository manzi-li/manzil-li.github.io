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
This version includes more advanced debugging.
-->

<div class="projects">
{%- assign sorted_teaching = site.teaching | sort: "importance" -%}

<!-- DEBUGGING: This will print all data for the first course found. -->

<strong>Full Course Data:</strong>

<pre><code>{{ sorted_teaching.first | inspect }}</code></pre>

<!-- Generate cards for each course -->

<div class="row row-cols-1 row-cols-md-3">
{%- for course in sorted_teaching -%}
{% include projects.liquid project=course %}
{%- endfor -%}
</div>
</div>