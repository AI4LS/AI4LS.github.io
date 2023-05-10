---
layout: page
permalink: /publications/
title: Publications
description: Publications of the group in the area of EDA. 
years: [2023,2022]
nav: true
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
