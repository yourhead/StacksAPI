---
name: Color
type: color
array: color-2, color-4
description: A color well for choosing colors.
value: HTML Color String
available: 2
generics: true
properties:

  - title: Opacity Enable
  - key: allowsOpacity
  - type: boolean
  - default: no
  - description: Enalbe the opacity slider on the color selection box.

  - title: Prefix
    key: prefix
    type: string
    default: #
    markdown: yes

  - title: Default Value
    key: default
    type: HTML Color String
    default: "Light gray: #ccc"
    description: The color the color well will be set to by default. If no color is provided light gray will be used.

---

A color well. 

When clicked the RapidWeaver shared color pallet is displayed. The selected color is converted to RGB and returned as a hex string.

{% include newstuff.html %}
### Opacity
The color control now allows you to enable opacity when selecting colors.  To ensure backward compatability it defaults to being disabled.

The default bevhavior of color values is now to output as rgba() css values instead of HTML hex colors.



{% include newstuff.html %}
### Color Array

Color controls can be used in arrays.  Each has its own subtitle and default, all other values are shared.  Color array types are:

- `color` : a regular color control.
- `color-2` : two color controls.
- `color-4` : four color controls.
