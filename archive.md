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
<h3>{{ tag[0] }}</h3>
<ul class="post-list" style="padding:0;">
	{% for post in tag[1] %}
<li><span class="post-meta">{{ post.date | date: "%B %Y" }}</span>
        <h3 style="margin:0;">
          <a href="{{ post.url }}" class="post-link"> {{ post.title }}</a>
        </h3></li>
		{% endfor %}
	</ul>
{% endfor %}


{%- assign allposts = site.posts | concat: site.misc | sort_natural: "date" | reverse %}

{%- assign postsByYearMonth = allposts | group_by_exp:"allposts", "allposts.date | date: '%Y %B'"  %}

{%- for yearMonth in postsByYearMonth %}
<h3>{{ yearMonth.name }}</h3>
<ul class="post-list" style="padding:0;">
  {%- for post in yearMonth.items %}
  <li>
	  <span class="post-meta">{{ post.date | date: "%B %Y" }}</span>
	  <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {%- endfor %}
</ul>
{%- endfor %}