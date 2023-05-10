---
layout: page
title: Paper Reading
permalink: /Paper Reading/
description: Most recent research works focus on proposing novel circuit representations, logic synthesis operators, synthesis sequence tuning algorithms, and physical aware synthesis to improve PPA or runtime.  Therefore, in the paper reading part, we will cover the above logic synthesis algorithms including those operators like rewrite, fraig, if, &nf, mfs2, and lutpack, which are also open-sourced in ABC, and recently proposed operators include MIG/XMG based operators like window rewriting, DB based operators like MFFW rewriting, and AI driven operators like SLAP. Based on them, heuristic and AI-driven synthesis tuning algorithms are developed to improve PPA or runtime. These algorithms include FlowTune, HIMap, BOiLS and EAC-RNN. With the physical guidance and constraints, logic synthesis can synthesize more physical design friendly netlists and directly optimize estimated timing instead of combinational logic depth. Currently, we only provide several paper reading note examples. More reading notes are coming soon.
nav: true
display_categories: [Logic Synthesis Operators, AI4LS Operators, Sequence Tuning]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
