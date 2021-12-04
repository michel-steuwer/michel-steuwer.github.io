---
layout: single
title: "Teaching"
permalink: /teaching/
author_profile: true
---

{% include base_path %}

I am (or have been) teaching the following courses.

{% for post in site.teaching reversed  %}
  {% capture this_year %}{{ post.year }}{% endcapture %}
  {% capture next_year %}{{ post.previous.year }}{% endcapture %}

  {% if forloop.first %}
  <h3 id="{{ this_year }}-ref">{{this_year}}</h3>
  <ul class="teaching">
  {% endif %}

  {% include teaching-item.html %}

  {% if forloop.last %}
  </ul>
  {% else %}
  {% if this_year != next_year %}
  </ul>
  <h3 id="{{ next_year }}-ref">{{next_year}}</h3>
  <ul>
  {% endif %}
  {% endif %}
{% endfor %}