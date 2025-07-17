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
This version includes debugging lines to help diagnose the issue.
-->

<!-- DEBUGGING STEP 1: This will print the total number of files found in your _teaching folder. -->

<p><strong>Debug Info:</strong> Number of teaching items found by Jekyll: <strong>{{ site.teaching.size }}</strong></p>

<div class="projects">
{%- assign sorted_teaching = site.teaching | sort: "importance" -%}
<!-- Generate cards for each course -->
{%- if page.horizontal -%}
<div class="container">
<div class="row row-cols-1 row-cols-md-2">
{%- for course in sorted_teaching -%}
<!-- DEBUGGING STEP 2: This will print the title of each course it tries to display. -->
<p><em>Processing course: {{ course.title }}</em></p>
{% include projects_horizontal.liquid project=course %}
{%- endfor -%}
</div>
</div>
{%- else -%}
<div class="row row-cols-1 row-cols-md-3">
{%- for course in sorted_teaching -%}
<!-- DEBUGGING STEP 2: This will print the title of each course it tries to display. -->
<p><em>Processing course: {{ course.title }}</em></p>
{% include projects.liquid project=course %}
{%- endfor -%}
</div>
{%- endif -%}
</div>