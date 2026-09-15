---
layout: single
title: "SHAPE Lab"
excerpt: "Simulation of Hazards, AI, People & Engineering Decisions"
permalink: /
author_profile: true
classes: home-page
header:
  overlay_image: "/images/home-banner.png"
  overlay_filter: 0.15
  image_description: "A calm panoramic view of distant wildfire smoke over a forest"
---

**SHAPE Lab** — **S**imulation of **H**azards, **A**I, **P**eople & **E**ngineering Decisions

*AI and decision science for people and infrastructure under natural hazards.*

## We SHAPE better decisions for people and infrastructure under natural hazards.

SHAPE Lab develops AI-enabled simulation and decision models to help individuals, communities, and infrastructure systems anticipate, prepare for, and respond to natural hazards. We study how natural hazards, engineered systems, institutions, and individual and collective decision-making interact across problems including wildfire behavior, risk analysis, evacuation, mitigation, and community resilience. Our interdisciplinary team of engineers, researchers, and students combines AI, engineering, and social science to address real-world risk and resilience challenges.

<div class="home-cta">
  <a class="home-cta-button home-cta-button--primary"
     href="{{ '/research/' | relative_url }}">
    Explore Our Research
  </a>

  <a class="home-cta-button home-cta-button--secondary"
     href="{{ '/people/' | relative_url }}">
    Meet the Team
  </a>
</div>

## Recent News

{% for post in site.posts limit: 3 %}
<div class="home-news-item">
  <strong>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </strong>
  <span>({{ post.date | date: "%B %Y" }})</span>

  {% assign summary = post.excerpt | default: post.content %}
  <div class="home-news-summary">
    {{ summary | strip_html | truncatewords: 35 }}
    <a href="{{ post.url | relative_url }}">Read more →</a>
  </div>
</div>
{% endfor %}
