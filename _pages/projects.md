---
layout: page
title: projects
permalink: /projects/
description: A snapshot of my research endeavours here.
nav: true
nav_order: 3
display_categories: [IS-AI-data, philosophy]
horizontal: false
---

🙋‍♂️ As one of the early global pioneers of Twitter research (ca. 2009), my PhD dissertation, "Inferring Social Behavior and Interaction on Twitter by Combining Metadata about Users & Messages", resulted in major contributions in social media metadata analysis and inference generation.
Since then, I am recognised as a subject-matter expert in social media analysis, as well as the research methods and computational techniques used - including Python programming, cloud computing, Tableau, Python, SQL - to name a few. My data analysis and research acumen have contributed to international research collaborations in a wide range of domains - from marketing, to mental health, to energy policy, to political science.

<hr/>

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
