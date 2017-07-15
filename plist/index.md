---
title: The Property List
layout: page
back:
  - top: /bundle
links:
  - plist: keys/assets
  - plist: keys/libraries
  - plist: keys/templates
---

The Info.plist file within a stack defines the basic attributes of the stack like its title and version number, the custom properties the stack will display when selected, and file names of each of the templates and assets.



{% assign groups = (site.keys | sort: 'group') %}
{% assign currentGroup = 'basic' %}

<ul>
<h3>{{ currentGroup | capitalize }}</h3>
{% for property in groups %}

  {% if property.group %}
    {% if currentGroup != property.group %}
      {% assign currentGroup = property.group %}
<br>      
<br>      
<h3>{{ currentGroup | capitalize }}</h3>

    {% endif %}
  {% endif %}

{% if property.available == site.version %}
    <li class='new'>
{% else %}
    {% if property.deprecated == site.version %}
        <li class='new deprecation'>
    {% else %}
        <li>
    {% endif %}
{% endif %}

<a href='{{ site.baseurl }}{{ property.url }}'>{{ property.name }}</a> &mdash; <code>{{ property.key }}</code> &mdash; {{ property.description }}</li>

{% endfor %}
</ul>