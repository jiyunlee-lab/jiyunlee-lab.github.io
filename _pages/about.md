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
     href="{{ '/publications/' | relative_url }}">
    View Publications
  </a>

  <a class="home-cta-button home-cta-button--secondary"
     href="{{ '/people/' | relative_url }}">
    Meet the Team
  </a>
</div>

<section class="home-research-tiles"
         aria-labelledby="home-research-title">

  <div class="home-research-heading">
    <h2 id="home-research-title">Research at a Glance</h2>

    <a href="{{ '/research/' | relative_url }}">
      View all research
      <i class="fas fa-arrow-right" aria-hidden="true"></i>
    </a>
  </div>

  {% assign home_themes = site.portfolio | sort: "order" %}

  <div class="home-research-grid">
    {% for theme in home_themes limit: 4 %}

      <a class="home-research-tile home-research-tile--{{ theme.accent | default: 'sage' }}"
         href="{{ theme.url | relative_url }}">

        <img src="{{ theme.home_image | relative_url }}"
             alt="{{ theme.title }} illustration"
             loading="lazy">

        <div class="home-research-tile-label">
          <h3>{{ theme.home_title | default: theme.title }}</h3>

          <i class="fas fa-arrow-right" aria-hidden="true"></i>
        </div>

      </a>

    {% endfor %}
  </div>

</section>

## Recent News

{% for post in site.posts %}
  <div class="home-news-item home-news-item--{{ post.news_type | default: 'news' }}"
       data-home-news-item>

    {% assign news_type = post.news_type | default: "news" %}
    {% assign news_label = "News" %}

    {% case news_type %}
      {% when "publication" %}
        {% assign news_label = "Publication" %}
      {% when "project" %}
        {% assign news_label = "Project" %}
      {% when "award" %}
        {% assign news_label = "Award" %}
      {% when "people" %}
        {% assign news_label = "People" %}
      {% when "media" %}
        {% assign news_label = "Media" %}
    {% endcase %}

    <span class="home-news-type home-news-type--{{ news_type }}">
      {{ news_label }}
    </span>

    <div class="home-news-heading">
      <strong>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </strong>

      <span class="home-news-date">
        ({{ post.date | date: "%B %Y" }})
      </span>
    </div>

    {% assign summary = post.excerpt | default: post.content %}

    <div class="home-news-summary">
      {{ summary | strip_html | truncatewords: 35 }}
      <a href="{{ post.url | relative_url }}">Read more →</a>
    </div>
  </div>
{% endfor %}

<div class="home-news-actions">

  <button type="button"
          id="home-news-more">
    Show older news
  </button>

  <a class="home-news-all"
     href="{{ '/year-archive/' | relative_url }}">
    View all news
    <i class="fas fa-arrow-right" aria-hidden="true"></i>
  </a>

</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const newsItems = Array.from(
    document.querySelectorAll("[data-home-news-item]")
  );

  const showMoreButton =
    document.getElementById("home-news-more");

  const initialNumber = 3;
  const batchSize = 3;
  let visibleNumber = initialNumber;

  function updateNewsVisibility() {
    newsItems.forEach(function (item, index) {
      item.hidden = index >= visibleNumber;
    });

    if (visibleNumber >= newsItems.length) {
      showMoreButton.hidden = true;
    } else {
      showMoreButton.hidden = false;
    }
  }

  showMoreButton.addEventListener("click", function () {
    visibleNumber += batchSize;
    updateNewsVisibility();
  });

  updateNewsVisibility();
});
</script>

