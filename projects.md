---
layout: page
title: Proyectos
---

{% for personal_project in site.personal_projects %}
  <h2>{{ personal_project.name }} - {{ personal_project.position }}</h2>
  <p>{{ personal_project.content | markdownify }}</p>
{% endfor %}

{% for personal_project in site.personal_projects %}
  <h2>
    <a href="{{ personal_project.url }}">
      {{ personal_project.name }} - {{ personal_project.position }}
    </a>
  </h2>
  <p>{{ personal_project.content | markdownify }}</p>
{% endfor %}