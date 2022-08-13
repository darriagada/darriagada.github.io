---
layout: page
title: Archivo
---

{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url }}">{{ post.date | date: "%B %Y" }} - {{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}



{% for tag in site.tags %}
<h2>{{ tag[0] }}</h2>
<ul>
	{% for post in tag[1] %}
<li><span class="post-date">
  {% assign m = page.date | date: "%-m" %}
  {% case m %}
    {% when '1' %}Ene
    {% when '2' %}Feb
    {% when '3' %}Mar
    {% when '4' %}Abr
    {% when '5' %}May
    {% when '6' %}Jun
    {% when '7' %}Jul
    {% when '8' %}Ago
    {% when '9' %}Sep
    {% when '10' %}Oct
    {% when '11' %}Nov
    {% when '12' %}Dic
  {% endcase %}
  {{ page.date | date: "%Y" }}</span>
        <h3>
          <a href="{{ post.url }}">{{ post.date | date: "%B %Y" }} - {{ post.title }}</a>
          </a>
        </h3></li>
		{% endfor %}
	</ul>
{% endfor %}