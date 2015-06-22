---
title: Controls
layout: page
back:
  - top: /plist
---


{% assign groups = (site.controls | sort: 'group') %}
{% assign currentGroup = 'basic' %}


<ul>
<h3>{{ currentGroup | capitalize }}</h3>
{% for control in groups %}

  {% if control.group %}
    {% if currentGroup != control.group %}
      {% assign currentGroup = control.group %}
<br>      
<br>      
<h3>{{ currentGroup | capitalize }}</h3>

    {% endif %}
  {% endif %}

<li><a href='{{ site.baseurl }}{{ control.url }}'>{{ control.name }}</a> &mdash; {{ control.description }}</li>

{% endfor %}
</ul>