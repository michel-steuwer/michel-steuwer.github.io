---
layout: single
title: "People I work with"
permalink: /people/
redirect_from:
  - /team/
author_profile: true
---
{% assign people = site.people | sort: 'start-year' | reverse | group_by: 'type' %}

<h2>PhD Students</h2>

{% for category in people %}
{% if category.name == "PhD Students" %}
  <!-- <h3 id="{{category.name | downcase | replace:' ','-'}}">{{category.name}}</h3> -->
  <ul>
    {% include people-items %}
  </ul>
{% endif %}
{% endfor %}

{% for category in people %}
{% if category.name == "Co-Supervised PhD Students" %}
  <h3 id="{{category.name | downcase | replace:' ','-'}}">{{category.name}}</h3>
  <ul>
    {% include people-items %}
  </ul>
{% endif %}
{% endfor %}

{% for category in people %}
{% if category.name == "Former PhD Students" %}
  <h3 id="{{category.name | downcase | replace:' ','-'}}">{{category.name}}</h3>
  <ul>
    {% include people-items %}
  </ul>
{% endif %}
{% endfor %}

{% for category in people %}
{% if category.name == "Former Co-Supervised PhD Students" %}
  <h3 id="{{category.name | downcase | replace:' ','-'}}">{{category.name}}</h3>
  <ul>
    {% include people-items %}
  </ul>
{% endif %}
{% endfor %}
