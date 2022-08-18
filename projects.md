---
layout: page
title: "Proyectos"
permalink: "/proyectos/"
---
{% for proyecto in site.proyectos %}
<ul class="post-list" style="padding:0;">
    <li>
  	  <span class="post-meta"><a href="#">Visitar</a></span>
	  <h3 style="margin:0;font-weight:100 !important;">
	   <a href="{{ proyecto.url }}" class="post-link">{{ proyecto.title }}</a>
	  </h3>
	  <p>{{ proyecto.stub }}</p>
  </li>
</ul>
{% endfor %}