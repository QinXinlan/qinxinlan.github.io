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

Scientific inquiry should be systematic, comprehensive, and adaptable to the complexities and uncertainties inherent to science, particularly in neuroscience. 

My academic focus centers on developing adaptive algorithms designed to address the significant variability present in neuroimaging data — especially electroencephalography (EEG) recordings — both within individuals and across subjects. I believe that achieving a high precision rate requires a multi-modal approach integrating various data modalities, including neuroelectromagnetic, physiological, behavioral, and muscular activity, alongside external environmental factors. This thorough approach allows to progressively build insights from the amalgamation of these diverse information sources.

Rigorously choosing each step in pipelines is crucial ifor determining the most effective strategies and methodologies to achieve generalizable results. With that in mind, let's begin by asking a few questions:


### 👀 Are blinks only noise for EEG signals? 👀
Yes, they are bigger than the background EEG. And yes, they are frequent. But should they be discarded?

### 🤖 Why choose this XX algorithm? 🤖
There are tons of available methods. Which one is best for pre-processing / filtering / classification / (any step of the pipeline)?

### ⚡ Why is the brain activity so different from one day to the other? ⚡
Sure, there are various physiological states / cognitive loads / environmental contexts / (any other dynamics). But there should be some kind of stability in brain regions for a specific task and individual, right?

### 🔎 How accurate is this XX result? 🔎
Pipeline A reaches 90% accuracy and pipeline B achieves 92% accuracy. Is the difference significant?


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
