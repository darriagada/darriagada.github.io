---
layout: page
title: "Proyectos"
permalink: "/proyectos/"
---
<style>
* {
  box-sizing: border-box;
}

.column {
  float: left;
  width: 240px;
  padding: 10px;
  margin-bottom:1rem;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

@media screen and (max-width: 600px) {
  .column {
    width: 100%;
  }
}
</style>

<ul class="post-list" style="padding:0;">
{% for proyecto in site.proyectos %}
    <li>
  	  <span class="post-meta"><a href="{{ proyecto.url }}" class="button">Visitar</a></span>
	  <h3 style="margin:0;font-weight:100 !important;">
	   <a href="{{ proyecto.url }}" class="post-link">{{ proyecto.title }}</a>
	  </h3>
	  <p>{{ proyecto.stub }}</p>
  </li>
{% endfor %}
</ul> 

<ul class="row">
{% for proyecto in site.proyectos %}
    <li class="column">
	  <a href="{{ proyecto.url }}"><img src="https://picsum.photos/400" alt="" /></a>
	  <h3 style="margin:0;font-weight:100 !important;">
	   <a href="{{ proyecto.url }}" class="post-link">{{ proyecto.title }}</a>
	  </h3>
	  <p>{{ proyecto.stub }}</p>
  </li>
{% endfor %}
</ul> 