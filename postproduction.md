---
layout: page
title: Portfolio
---

## Post-Production
<div class="grid">
{% assign items = site.projects | where: "category", "Post" | sort: "date" | reverse %}
{% for p in items %}
  {% include project-card.html p=p %}
{% endfor %}
</div>
