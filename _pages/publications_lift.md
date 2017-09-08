---
layout: single
title: "Publications related to the [Lift project](http://www.lift-project.org/)"
permalink: /publications-lift/
author_profile: true
---

{% include base_path %}

{% assign last_year = '' %}
{% assign need_to_close_ul = false %}

{% for post in site.publications reversed  %}
{% if post.projects contains 'Lift' %}
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