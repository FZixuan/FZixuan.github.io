---
layout: page
permalink: /teaching/
title: Teaching
#description: Materials for courses you taught. Replace this text with your description.
nav: true
nav_order: 2 #6
display_categories: [Instructor, Grader]
horizontal: false
---

<!-- pages/teaching.md -->
<div class="teaching">
    {% if site.enable_project_categories and page.display_categories %}
      <!-- Display categorized teaching -->
      {% for category in page.display_categories %}
      <a id="{{ category }}" href=".#{{ category }}">
        <h2 class="category">{{ category }}</h2>
      </a>
      {% assign categorized_teaching = site.teaching | where: "category", category %}
      {% assign sorted_teaching = categorized_teaching | sort: "date" | reverse %}
      {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-1 row-cols-md-2">
        {% for teaching in sorted_teaching %}
            <div class="d-flex justify-content-between mb-2">
                <!-- Left aligned class_name -->
                <span>{{ teaching.title }}</span>
                <!-- Right aligned time -->
                {% if teaching.time %}
                    <span>{{ teaching.time }}</span>
                {% endif %}
            </div>
            {% if teaching.description %}
                <!-- Description in italic if it exists -->
                <div class="text-muted" style="font-style: italic;">
                {{ teaching.description }}
                </div>
            {% endif %}
        {% endfor %}
        </div>
      </div>
      {% else %}
      <div class="row row-cols-1 row-cols-md-3">
        {% for teaching in sorted_teaching %}
            <div class="d-flex justify-content-between mb-2">
                <!-- Left aligned title -->
                <span>{{ teaching.title }}</span>
                <!-- Right aligned time (if exists) -->
                {% if teaching.time %}
                    <span>{{ teaching.time }}</span>
                {% endif %}
            </div>
            {% if teaching.description %}
                <!-- Description in italic if it exists -->
                <div class="text-muted" style="font-style: italic;">
                {{ teaching.description }}
                </div>
            {% endif %}
        {% endfor %}
      </div>
      {% endif %}
      {% endfor %}
    {% else %}
    <!-- Display projects without categories -->
    {% assign sorted_teaching = site.teaching | sort: "date" | reverse %}
    {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-1 row-cols-md-2">
        {% for teaching in sorted_teaching %}
            <div class="d-flex justify-content-between mb-2">
                <!-- Left aligned class_name -->
                <span>{{ teaching.title }}</span>
                <!-- Right aligned time -->
                {% if teaching.time %}
                    <span>{{ teaching.time }}</span>
                {% endif %}
            </div>
            {% if teaching.description %}
                <!-- Description in italic if it exists -->
                <div class="text-muted" style="font-style: italic;">
                {{ teaching.description }}
                </div>
            {% endif %}
        {% endfor %}
        </div>
      </div>
    {% else %}
      <div class="row row-cols-1 row-cols-md-3">
        {% for teaching in sorted_teaching %}
            <div class="d-flex justify-content-between mb-2">
                <!-- Left aligned title -->
                <span>{{ teaching.title }}</span>
                <!-- Right aligned time (if exists) -->
                {% if teaching.time %}
                    <span>{{ teaching.time }}</span>
                {% endif %}
            </div>
            {% if teaching.description %}
                <!-- Description in italic if it exists -->
                <div class="text-muted" style="font-style: italic;">
                {{ teaching.description }}
                </div>
            {% endif %}
        {% endfor %}
      </div>
      {% endif %}
    {% endif %}

</div>
