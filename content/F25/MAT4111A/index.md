---
title: 'MAT 4111A: Putnam Preparation'
term: F25
courseNumber: MAT4111A
layout: layouts/base.njk
---

<h1 style="margin:0;">MAT 4111A</h1>
<h4 style="margin:0;">Putnam Preparation</h4>

<a href="/F25/MAT4111A/student-selected/">Student selected problems</a>

<a href="/F25/MAT4111A/proof_techniques/"><h2>Proof techniques</h2></a>
<ul>
  {% for post in collections.proof_techniques %}
    <li>
      {% if post.data.week %} Week {{post.data.week}}:{% endif %} <a href="{{ post.url }}">{{ post.data.title }}</a>
    </li>
  {% endfor %}
</ul>

## End-of-term write-ups
<ul>
{% for post in collections.all %}
  {% if post.data.courseNumber == "MAT4111A" and post.data.term == "F25" and post.data.type == "assignment" %}
    <li><a href="{{ post.url }}">{{ post.data.title }}</a> </li>
  {% endif %}
{% endfor %}
</ul>
