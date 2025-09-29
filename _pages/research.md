---
title: "Research Projects"
permalink: /research/
layout: single
author_profile: true
---

Here is a selection of my research projects. 

(Under Construction) Click on any project to learn more about the methodology and results.

<div class="feature__wrapper">
{% for project in site.data.projects %}
  <div class="feature__item--left">
    <div class="archive__item">
      <div class="archive__item-teaser">
        <img src="{{ project.image_path | relative_url }}" alt="{{ project.title }} teaser image">
      </div>
      <div class="archive__item-body">
        <h2 class="archive__item-title">{{ project.title }}</h2>
        <div class="archive__item-excerpt">
          <p>{{ project.excerpt }}</p>
        </div>
        <p><a href="{{ project.url }}" class="btn btn--inverse">Learn More</a></p>
      </div>
    </div>
  </div>
{% endfor %}
</div>