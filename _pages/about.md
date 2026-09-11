---
layout: single
title: "SHAPE Lab"
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

Our research group explores how people, disasters, and the built environment interact in an increasingly complex world. We combine AI, simulation, data analytics, and decision science to understand human behavior and engineered systems under natural hazards and to develop smarter ways to anticipate, respond to, and manage risk. We are an interdisciplinary team of engineers, researchers, and students working at the intersection of humans, AI, and infrastructure to address real-world challenges.

## Recent News

{% for post in site.posts limit:2 %}
**[{{ post.title }}]({{ post.url | relative_url }})** ({{ post.date | date: "%B %Y" }})<br>
{{ post.content }}

{% endfor %}
