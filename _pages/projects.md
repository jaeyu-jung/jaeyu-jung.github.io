---
layout: page
title: Research
permalink: /Research/
description:
nav: true
nav_order: 3
display_categories: [Working Papers, Works in Progress]
horizontal: false
---
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
    {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  
  <div class="container mt-4"> {% comment %} 컨테이너를 사용하여 페이지 폭 조절 {% endcomment %}
    <div class="row justify-content-center"> {% comment %} 중앙 정렬 {% endcomment %}
      <div class="col-12 col-lg-10"> {% comment %} 큰 화면에서는 10/12 폭, 작은 화면에서는 전체 폭 {% endcomment %}
        {% for project in sorted_projects %}
          {% comment %}
            {% include projects.liquid %}
          {% endcomment %}
          {% include projects_list.liquid %}
        {% endfor %}
      </div>
    </div>
  </div>
  {% endfor %}

{% else %}

{% assign sorted_projects = site.projects | sort: "importance" %}

  <div class="container mt-4">
    <div class="row justify-content-center">
      <div class="col-12 col-lg-10">
        {% for project in sorted_projects %}
          {% comment %}
            {% include projects.liquid %}
          {% endcomment %}
        {% include projects_list.liquid %}
        {% endfor %}
      </div>
    </div>
  </div>

{% endif %}
</div>

{% comment %}
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
      {% comment %}
      {% include projects.liquid %}
      {% endcomment %}
    {% include projects_list.liquid %}
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
{% endcomment %}
