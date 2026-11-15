---
layout: splash
title: "Leon Jiang"
tagline: "I build robots and cool things :)"
header:
  overlay_image: /assets/img/posts/bearing/bearing.jpg
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
math: true
---

<!-- <section class="intro">
  <p class="intro__lead">I'm Leon — a maker and engineering student based in Vancouver. I spend my time designing parts, building fixtures, and figuring out why the first version didn't work.</p>
  <p>This is my workshop notebook: project write-ups, build logs, and the occasional tip that saves someone else a broken part.</p>
</section> -->

<section id="projects" class="projects">
  <div class="projects__header">
    <h1>Projects</h1> 
    <hr>
    <!-- <p>A selection of builds from the bench. Click any card for the full write-up.</p> -->
  </div>
  {% include project-grid.html %}
</section>

<section id="posts" class="posts">
  <div class="posts__header">
    <h1>Blog Posts</h1>
    <hr>
  </div>
  <div class="entries-list">
    {% include documents-collection.html entries=site.posts type='list' %}
  </div>
  {% include paginator.html %}
</section>
