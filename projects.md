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
  width: 50%;
  padding: 1.3rem;
  margin-bottom:.5rem;
}

.projects-list {
	margin:0 !important;
	padding:0 !important;
	list-style-type:none;
}

.row:after {
  content: "";
  display: table;
  clear: both;
}

.column a img {
	opacity:1;
}

.column a:hover img {
	opacity:0.5;
}

.page-title {
	display:none;
}

@media screen and (max-width: 600px) {
  .column {
    width: 100%;
  }
}
</style>

<ul class="row projects-list">
{% for proyecto in site.proyectos %}
    <li class="column">
	  <a href="{{ proyecto.url }}"><img src="{{ proyecto.thumb }}" alt="{{ proyecto.title }}" /></a>
	  <h3 style="margin:0;font-weight:100 !important;">
	   <a href="{{ proyecto.url }}" class="post-link">{{ proyecto.title }}</a>
	  </h3>
	  <p>{{ proyecto.stub }}</p>
  </li>
{% endfor %}
</ul> 