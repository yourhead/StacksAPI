---
title: Controls
layout: page
back:
  - top: /plist
links:
  - top: /templates
---

#### Control Arrays

Many control types now support array types: a group of related controls.  Control arrays share many of the same properties like `id`, `title`, and `enable`, etc. However their `default` and `subtitles` become arrays.

To access an array value use the the property's template, then adding an array index such as `%id=myValue[2]`. See the [Property Value template](/templates/value/) documentation for more info.

#### Subtitles
Most controls can now display a subtitle.  Subtitles provide more contextual info and are especially helpful in array controls so that each control can be labeled. Omitting the label makes the control vertically more compact.

> Note: Four-across control arrays have very limited space for subtitles.

{% assign groups = (site.controls | sort: 'group') %}
{% assign currentGroup = 'basic' %}


## Controls
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


{% if control.available == site.version %}
    <li class='new'>
{% else %}
    {% if control.deprecated == site.version %}
        <li class='new deprecation'>
    {% else %}
        <li>
    {% endif %}
{% endif %}

<a href='{{ site.baseurl }}{{ control.url }}'>{{ control.name }}</a> &mdash; {{ control.description }}</li>

{% endfor %}
</ul>
