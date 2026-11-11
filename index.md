---
layout: splash
title: "Leon Jiang"
tagline: "I build robots and cool things :)"
header:
  overlay_image: /assets/images/bearing/bearing.jpg
  overlay_filter: 0.55
  image_description: "Ball bearing"
  # actions:
  #   - label: "View Projects"
  #     url: "#projects"
  #   - label: "About Me"
  #     url: /about/
  #   - label: "GitHub"
  #     url: https://github.com/the-relentless-epee
author_profile: true
---

<!-- <section class="intro">
  <p class="intro__lead">I'm Leon — a maker and engineering student based in Vancouver. I spend my time designing parts, building fixtures, and figuring out why the first version didn't work.</p>
  <p>This is my workshop notebook: project write-ups, build logs, and the occasional tip that saves someone else a broken part.</p>
</section> -->

<section id="projects" class="projects">
  <div class="projects__header">
    <h2>Projects</h2> 
    <!-- <p>A selection of builds from the bench. Click any card for the full write-up.</p> -->
  </div>

  {% assign projects = site.projects | sort: 'order' %}
  <div class="project-grid">
    {% for project in projects %}
    <a class="project-card" href="{{ project.url | relative_url }}">
      <div class="project-card__thumb">
        <img src="{{ project.thumbnail | relative_url }}" alt="{{ project.title | escape }}" loading="lazy">
      </div>
      <div class="project-card__body">
        <h3 class="project-card__title">{{ project.title }}</h3>
        <p class="project-card__summary">{{ project.summary | default: project.excerpt | strip_html | truncate: 120 }}</p>
        <span class="project-card__cta">View project &rarr;</span>
      </div>
    </a>
    {% endfor %}
  </div>
</section>

<section id="posts" class="posts">
  <h2 class="archive__subtitle">Recent Posts</h2>
  <div class="entries-list">
    {% include documents-collection.html entries=site.posts type='list' %}
  </div>
  {% include paginator.html %}
</section>
