---
layout: page
title: "Proyectos"
permalink: "/proyectos/"
---

{% for proyecto in site.proyectos %}
  <h2>
    <a href="{{ proyecto.url }}">
      {{ proyecto.title }}
    </a>
  </h2>
  <p>{{ proyecto.stub | markdownify }}</p>
  <!--<p>{{ proyecto.content | markdownify }}</p>-->
{% endfor %}