---
title: Team
icon: fa-users
position: 3
---

### PhD Students

{% assign current_students = site.people | where:'type', "PhD Students" | sort: "start-year" | reverse %}

<div class="row">
{% for student in current_students %}
    {% include current-student.html %}
{% endfor %}
</div>

### Former Students

{% assign former_students = site.people | where:'type', "Former PhD Students" | sort: "end-year" | reverse %}

<ul>
{% for student in former_students %}
    {% include former-student.html %}
{% endfor %}
</ul>