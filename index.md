---
layout: default
---

<section class="hero">
  <h1>Audio Engineer</h1>
  <p>{{ site.description }} · Based in Europe</p>

  <div class="btns">
    <a class="btn primary" href="/music/">Music Portfolio</a>
    <a class="btn primary" href="/postproduction/">Post Production Portfolio</a>
    <a class="btn" href="/assets/files/IkerElvi_CV.pdf">Download CV</a>
    <a class="btn" href="/contact/">Contact</a>
  </div>
</section>

<section>
  <h2>Featured Work</h2>
  <p class="muted">A selection of projects in music, post-production and game audio.</p>

  <!--div class="grid">
  {% assign featured = site.projects | where: "featured", true | sort: "date" | reverse %}
  {% for p in featured limit: 4 %}
    {% include project-card.html p=p %}
  {% endfor %}
  </div-->
</section>



