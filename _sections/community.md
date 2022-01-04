---
title: Community Activities
nav-title: Community
icon: fa-globe-africa
position: 6
---

{% include committee_types %}

{% for type in types %}
  {% if type == '' %} {% continue %} {% endif %}

<div class="subsection">
    <span class="highlight"><strong>{{type}}</strong></span> of
    <ul class="inline">
{% for comittee in site.committees %}
{% if comittee.type contains type %}
    {% for year in comittee.years %}
        {% if forloop.first %}
            <li><a href="{{comittee.link}}">{{comittee.name}}</a> {{year}}</li>
        {% else %}
            <li>{{year}}</li>
        {% endif %}
    {% endfor %}
    {% if comittee.since %}
        <li><a href="{{comittee.link}}">{{comittee.name}}</a> since {{comittee.since}}</li>
    {% endif %}
{% endif %}
{% endfor %}
    </ul>
</div>

{% endfor %}