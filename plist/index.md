---
title: The Property List
layout: page
back:
  - top: /bundle
links:
  - plist: controls
  - plist: templates
  - plist: assets
---

Overview
The Info.plist file within a stack defines the basic attributes of the stack like its title and version number, the custom properties the stack will display when selected, and file names of each of the templates and assets.



{% assign groups = (site.keys | sort: 'group') %}
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

<li><a href='{{ site.baseurl }}{{ control.url }}'>{{ control.name }}</a> &mdash; <code>{{ control.key }}</code> &mdash; {{ control.description }}</li>

{% endfor %}
</ul>