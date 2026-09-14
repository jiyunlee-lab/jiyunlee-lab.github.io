---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

Our research is inherently interdisciplinary, drawing on a wide range of methods — including AI and machine learning, stochastic and computational simulation, engineering models, and social science approaches such as interviews and surveys — to tackle large-scale, uncertain, and complex risk problems across the themes below.

{% assign research_themes = site.portfolio | sort: "order" %}

<div class="research-theme-grid">
  {% for post in research_themes %}
    <a
      class="research-theme-card research-theme-card--{{ post.accent | default: 'sage' }}"
      href="{{ post.url | relative_url }}"
      aria-label="Learn more about {{ post.title }}"
    >
      <span class="research-theme-icon" aria-hidden="true">
        <i class="{{ post.icon }}"></i>
      </span>

      <h2 class="research-theme-title">
        {{ post.title }}
      </h2>

      <p class="research-theme-description">
        {{ post.excerpt }}
      </p>

      <span class="research-theme-link">
        Explore theme
        <i class="fas fa-arrow-right" aria-hidden="true"></i>
      </span>
    </a>
  {% endfor %}
</div>
