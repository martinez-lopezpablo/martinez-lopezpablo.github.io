---
layout: page
permalink: /outreach/
title: outreach
description: Until now, all my outreach work has been in Spanish. Sorry!
nav: true
nav_order: 4
---

<div class="outreach-list">
  {% assign items = site.outreach | sort: "date" | reverse %}
  {% for item in items %}
    <article class="outreach-card">
      <div class="outreach-text">
        <h3 class="outreach-title">
          {% if item.link %}
            <a href="{{ item.link }}" target="_blank" rel="noopener noreferrer">
              {{ item.title }}
            </a>
          {% else %}
            {{ item.title }}
          {% endif %}
        </h3>
        {% if item.subtitle %}
          <p class="outreach-subtitle">{{ item.subtitle }}</p>
        {% endif %}
        <p class="outreach-meta">
          {% if item.date %}{{ item.date | date: "%d %b %Y" }}{% endif %}
          {% if item.venue %} · {{ item.venue }}{% endif %}
          {% if item.location %} · {{ item.location }}{% endif %}
        </p>
      </div>

      {% if item.image %}
        <div class="outreach-thumb">
          <img src="{{ item.image | relative_url }}" alt="{{ item.title }}">
        </div>
      {% endif %}
    </article>
  {% endfor %}
</div>
