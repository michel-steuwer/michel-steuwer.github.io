---
layout: single
title: "Publications by Project"
permalink: /publications-by-project/
author_profile: true
---
{% include base_path %}

{% assign projects =  "RISE, ELEVATE, Lift, PACXX, GPU Compilation for Interpreted Languages, Marawacc, SkelCL, dOpenCL" | split: ", " %}

 {% if site.author.googlescholar or site.author.dblp %} 
  You can also find my publications on {% if site.author.dblp %} <a href="{{site.author.dblp}}">my dblp profile</a> {% endif %} {% if site.author.googlescholar and site.author.dblp %} and {% endif %} {% if site.author.googlescholar %} <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>{% endif %}.
 {% endif %}

<h3>Research Projects</h3>
<ul style="padding-left: 2em;">
{% for project in projects  %}
  {% if project == '' %}
    {% continue %}
  {% endif %}
<li style="display: inline; float:left; list-style-type: none; margin-right: 1em; margin-bottom: 0em;"><strong><a href="#{{project | downcase | replace:' ','-'}}">{{project}}</a></strong></li>
{% endfor %}
</ul>
<div style="clear: both; padding-bottom: .5em;"></div>
You find my publications also [organised by publication date](/publications/) and [organised by type](/publications-by-type/).

{% for project in projects %}
  {% if project == '' %}
    {% continue %}
  {% endif %}
  <h3 id="{{project | downcase | replace:' ','-'}}">{{ project }}</h3>
  <ul style="padding-left: 20px">

{% assign last_year = '' %}
{% assign need_to_close_ul = false %}

{% for post in site.publications reversed  %}
{% if post.projects contains project %}
  {% capture year %}{{ post.date | date: "%Y" }}{% endcapture %}
  {% if year != last_year %}
    {% if last_year != '' %}
</ul>
</li>
    {% endif %}
<li style="list-style-type: none;">
<h4 style="margin-top: 0px;" id="{{ year }}-ref">{{year}}</h4>
<ul>
  {% assign need_to_close_ul = true %}
  {% capture last_year %}{{year}}{% endcapture %}
  {% endif %}

  {% include publication-item.html %}
{% endif %}
{% endfor %}

{%if need_to_close_ul %}
</ul>
</li>
{% endif %}

  </ul>
{% endfor %}
