---
layout: page
title: Proyectos
---

{% for project in site.projects %}
  <h2>{{ project.name }} - {{ project.position }}</h2>
  <p>{{ project.content | markdownify }}</p>
{% endfor %}

{% for project in site.projects %}
  <h2>
    <a href="{{ project.url }}">
      {{ project.name }} - {{ project.position }}
    </a>
  </h2>
  <p>{{ project.content | markdownify }}</p>
{% endfor %}