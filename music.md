---
layout: page
title: Music Portfolio
---

## Music
<div class="grid">
{% assign items = site.projects | where: "category", "Music" | sort: "date" | reverse %}
{% for p in items %}
  {% include project-card.html p=p %}
{% endfor %}
</div>