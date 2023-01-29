---
title: Template Variables
layout: page
back:
  - top: /bundle
links:
  - plist: keys/templates  
  - plist: plist/controls  
---


### Overview
Templates are files that define the content of your stack. You can have any number of templates in your stack. They're specified in the Info.plist [Templates Dictionary](/keys/templates/).  The template variables listed below will be replaced in each template.



{% assign groups = (site.templates | sort: 'group') %}
{% assign currentGroup = 'basic' %}


<ul>
<h3>{{ currentGroup | capitalize }}</h3>
{% for template in groups %}

  {% if template.group %}
    {% if currentGroup != template.group %}
      {% assign currentGroup = template.group %}
<br>      
<br>      
<h3>{{ currentGroup | capitalize }}</h3>

    {% endif %}
  {% endif %}



{% if template.available == site.version %}
    <li class='new'>
{% else %}
    {% if template.deprecated == site.version %}
        <li class='new deprecation'>
    {% else %}
        <li>
    {% endif %}
{% endif %}

<a href='{{ site.baseurl }}{{ template.url }}'>{{ template.name }}</a> &mdash; {{ template.description }}</li>

{% endfor %}
</ul>
