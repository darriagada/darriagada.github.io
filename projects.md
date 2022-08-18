---
layout: page
title: "A list of animals"
permalink: "/proyectos/"
---

{% for proyecto in site.proyectos %}
  <h2>
    <a href="{{ proyecto.url }}">
      {{ proyecto.name }} - {{ proyecto.position }}
    </a>
  </h2>
  <p>{{ proyecto.content | markdownify }}</p>
{% endfor %}