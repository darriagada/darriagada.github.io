---
layout: page
title: Archivo
---

{%- assign allposts = site.posts | sort_natural: "date" | reverse %}

{%- assign postsByYearMonth = allposts | group_by_exp:"allposts", "allposts.date | date: '%Y'"  %}

{%- for yearMonth in postsByYearMonth %}
<h2>{{ yearMonth.name }}</h2>
<ul class="post-list" style="padding:0;">
  {%- for post in yearMonth.items %}
  <li>
	  <span class="post-meta">
      {% assign m = post.date | date: "%-m" %}
      {{ post.date | date: "%-d" }}
      {% case m %}
        {% when '1' %}Enero
        {% when '2' %}Febrero
        {% when '3' %}Marzo
        {% when '4' %}Abril
        {% when '5' %}Mayo
        {% when '6' %}Junio
        {% when '7' %}Julio
        {% when '8' %}Agosto
        {% when '9' %}Septiembre
        {% when '10' %}Octubre
        {% when '11' %}Noviembre
        {% when '12' %}Diciembre
      {% endcase %}
      {{ post.date | date: "%Y" }}
	  </span>
	  <h3 style="margin:0;font-weight:100 !important;">
	   <a href="{{ post.url }}" class="post-link">{{ post.title }}</a>
	  </h3>
  </li>
  {%- endfor %}
</ul>
{%- endfor %}