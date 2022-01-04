---
title: Talks
icon: fa-comment
position: 5
---

{% for talk in site.talks reversed %}
{% capture this_year %}{{talk.date | date: "%Y"}}{% endcapture %}
{% capture next_year %}{{talk.previous.date | date: "%Y"}}{% endcapture %}
{% if forloop.first %}
<div><span class="year">{{this_year}}</span></div>
{% endif %}
    {% include talk-item.html %}
{% if forloop.last %}
{% else %}
    {% if this_year != next_year %}
<div><span class="year">{{next_year}}</span></div>
    {% endif %}
{% endif %}
{% endfor %}
