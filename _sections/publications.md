---
title: Publications
icon: fa-book-open
position: 4
---

<p>You can also find my publications on my <a href="https://dblp.uni-trier.de/pers/hd/s/Steuwer:Michel"><i class="ai ai-dblp color1" aria-hidden="true"></i> dblp profile</a> and my <a href="https://scholar.google.com/citations?user=XdXJRZEAAAAJ"><i class="ai ai-google-scholar color1" aria-hidden="true"></i> Google Scholar</a> profile.</p>

{% for paper in site.publications reversed %}
{% capture this_year %}{{ paper.date | date: "%Y" }}{% endcapture %}
{% capture next_year %}{{ paper.previous.date | date: "%Y" }}{% endcapture %}
{% if forloop.first %}
<div><span class="year">{{this_year}}</span></div>
{% endif %}
{% include pub-item.html %}
{% if forloop.last %}
{% else %}
    {% if this_year != next_year %}
<div><span class="year">{{next_year}}</span></div>
    {% endif %}
{% endif %}

{% endfor %}
