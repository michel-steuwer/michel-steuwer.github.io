---
layout: single
title: "Publications Organised by Research Project"
permalink: /publications-by-project/
author_profile: true
---
{% include base_path %}

{% assign projects =  "RISE, ELEVATE, Lift, PACXX, GPU Compilation for Interpreted Languages, Marawacc, SkelCL, dOpenCL" | split: ", " %}

 {% if site.author.googlescholar or site.author.dblp %} 
  You can also find my publications on {% if site.author.dblp %} <a href="{{site.author.dblp}}">my dblp profile</a> {% endif %} {% if site.author.googlescholar and site.author.dblp %} and {% endif %} {% if site.author.googlescholar %} <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>{% endif %}.
 {% endif %}

You find my publications also [organised by publication date](/publications/) and [organised by type](/publications-by-type/).

<h3>Research Projects</h3>
<ul style="padding-left: 2em;">
{% for project in projects  %}
  {% if project == '' %}
    {% continue %}
  {% endif %}
<li style="margin-bottom: 0em;"><strong><a href="#{{project | downcase | replace:' ','-'}}">{{project}}</a></strong></li>
{% endfor %}
</ul>

{% for project in projects %}
  {% if project == '' %}
    {% continue %}
  {% endif %}
  <h2 id="{{project | downcase | replace:' ','-'}}">{{ project }}</h2>
  <ul>

{% assign last_year = '' %}
{% assign need_to_close_ul = false %}

{% for post in site.publications reversed  %}
{% if post.projects contains project %}
  {% capture year %}{{ post.date | date: "%Y" }}{% endcapture %}
  {% if year != last_year %}
    {% if last_year != '' %}
</ul>
    {% endif %}
<h3 id="{{ year }}-ref">{{year}}</h3>
<ul>
  {% assign need_to_close_ul = true %}
  {% capture last_year %}{{year}}{% endcapture %}
  {% endif %}

  {% include publication-item.html %}
{% endif %}
{% endfor %}

{%if need_to_close_ul %}
</ul>
{% endif %}

  </ul>
{% endfor %}
