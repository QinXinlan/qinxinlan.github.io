---
page_id: projects
layout: page-descript # page
title: Projects # Overview
permalink: /projects/
description: One Few Over the Projects' Nest
nav: false # true
nav_order: 3
horizontal: false
# display_categories: [work, fun]
dropdown: true
children:
  - title: Overview
    permalink: /projects/
  - title: divider
  - title: Blinks
    permalink: /projects/1_project/
  - title: divider
  - title: Algorithms
    permalink: /projects/2_project/
  - title: divider
  - title: Variability
    permalink: /projects/3_project/
  - title: divider
  - title: Statistics
    permalink: /projects/4_project/
---


## 💡 Philosophy 💡

Scientific inquiry should be systematic, comprehensive, and adaptable to the complexities and uncertainties inherent to science, and especially neuroscience. 

At the core of my academic focus lies the development of adaptive algorithms capable of mitigating the substantial variability inherent in neuroimaging - and specifically electroencephalography (EEG) - recordings, both within individuals and across subjects. I believe that achieving a high precision rate requires a multi-modal strategy integrating diverse data modalities, including neuroelectromagnetic, physiological, behavioral, and muscular activity, alongside external environmental factors, to gradually accumulate insights from this amalgamation of information sources. 

Rigorously choosing each step in pipelines is crucial in determining the most suitable strategies and methodologies for achieving generalizable results. Let's start by asking a few questions:


👀 Why are blinks noise for EEG signals? 👀

🤖 Why choose this XX algorithm? 🤖

⚡ Why is the brain activity for a specific task and a specific individual so different from one day to the other? ⚡

🔎 How accurate is this XX result? 🔎



---

<!-- pages/projects.md -->
<div class="projects">
  {% if site.enable_project_categories and page.display_categories %}
    <!-- Display categorized projects -->
    {% for category in page.display_categories %}
      <a id="{{ site.data[site.active_lang].strings.categories[category] }}" href=".#{{ site.data[site.active_lang].strings.categories[category] }}">
        <h2 class="category">{{ site.data[site.active_lang].strings.categories[category] }}</h2>
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
