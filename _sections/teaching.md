---
title: Teaching
icon: fa-chalkboard-teacher
position: 7
---

I am and have been teaching the following courses.

{% for course in site.teaching reversed %}
{% capture this_year %}{{course.year}}{% endcapture %}
{% capture next_year %}{{course.previous.year}}{% endcapture %}
{% if forloop.first %}
<div><span class="year">{{this_year}}</span></div>
<ul>
{% endif %}

<li><strong>{{course.title}}</strong>, {{course.type}}, {{course.notes}}</li>

{% if forloop.last %}
</ul>
{% else %}
    {% if this_year != next_year %}
</ul>
<div><span class="year">{{next_year}}</span></div>
<ul>
    {% endif %}
{% endif %}

{% endfor %}