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
  padding: 0 1.5rem .9rem 1.5rem;
  margin-bottom:0;
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
	padding: 0 .5rem .9rem .5rem;
  }
  
  .logo {margin:0 auto !important;}
}
</style>

<ul class="row projects-list">
{% for proyecto in site.proyectos reversed %}
    <li class="column">
	  <a href="{{ proyecto.url }}"><img src="{{ proyecto.thumb }}" alt="{{ proyecto.title }}" /></a>
	  <h3 style="margin:0;font-weight:100 !important;">
	   <a href="{{ proyecto.url }}" class="post-link">{{ proyecto.title }}</a>
	  </h3>
	  <p>{{ proyecto.stub }}</p>
  </li>
{% endfor %}
</ul> 

<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ paginator.next_page_path | absolute_url }}">Proyectos antiguos</a>
  {% else %}
    <span class="pagination-item older">Proyectos antiguos</span>
  {% endif %}
  {% if paginator.previous_page %}
    {% if paginator.page == 2 %}
      <a class="pagination-item newer" href="{{ '/' | absolute_url }}">Proyectos nuevos</a>
    {% else %}
      <a class="pagination-item newer" href="{{ paginator.previous_page_path | absolute_url }}">Proyectos nuevos</a>
    {% endif %}
  {% else %}
    <span class="pagination-item newer">Proyectos nuevos</span>
  {% endif %}
</div>