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
  <h3 id="{{category.name | downcase | replace:' ','-'}}">{{category.name}}</h3>
  <ul>
    {% include people-items %}
  </ul>
{% endif %}
{% endfor %}

{% for category in people %}
{% if category.name == "Co-Supervised PhD Students" %}
  <h3 id="{{category.name | downcase | replace:' ','-'}}">{{category.name}}</h3>
  <ul>
{% for person in category.items %}

  <li class="{{ include.type | default: "list" }}__item" style="list-style-type: none; width: 100%; display: block; overflow: auto;">
  <div style="float: left; width: 10%">
      <img src="{{base_path}}/{{ person.picture }}" style="width: 100%;"/>
  </div>
  <div style="float: left; width: 90%; padding-left: 2%;">
    <p>
      <a href="{{ person.link }}">
        <b>{{ person.name }}</b>: <i>{{ person.topic }}</i>
      </a><br/>
      <span style="font-size: 90%;">since: {{ person.start-year }}</span>.
      <span style="font-size: 75%;">Supervised together with {{ person.with }}</span>
    </p>
  </div>
  <div style="clear:both;"></div>
  </li>

{% endfor %}
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
{% for person in category.items %}

  <li class="{{ include.type | default: "list" }}__item" style="list-style-type: none; width: 100%; display: block; overflow: auto;">
  <div style="float: left; width: 10%">
      <img src="{{base_path}}/{{ person.picture }}" style="width: 100%;"/>
  </div>
  <div style="float: left; width: 90%; padding-left: 2%;">
    <p>
      <a href="{{ person.link }}">
        <b>{{ person.name }}</b>: <i>{{ person.topic }}</i>
      </a><br/>
      <span style="font-size: 90%;">{{ person.start-year }} - {{ person.end-year }}</span>.
      <span style="font-size: 75%;">Supervised together with {{ person.with }}</span>
      <br/>
      <span style="font-size: 90%;">Now {{ person.now }}</span>
    </p>
  </div>
  <div style="clear:both;"></div>
  </li>

{% endfor %}
  </ul>
{% endif %}
{% endfor %}
