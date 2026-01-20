---
layout: page
title: Portfolio
---

## Music
<div class="grid">
{% assign items = site.projects | where: "category", "Music" | sort: "date" | reverse %}
{% for p in items %}
  {% include project-card.html p=p %}
{% endfor %}
</div>

## Post-Production
<div class="grid">
{% assign items = site.projects | where: "category", "Post" | sort: "date" | reverse %}
{% for p in items %}
  {% include project-card.html p=p %}
{% endfor %}
</div>

## Game Audio
<div class="grid">
{% assign items = site.projects | where: "category", "Game Audio" | sort: "date" | reverse %}
{% for p in items %}
  {% include project-card.html p=p %}
{% endfor %}
</div>
