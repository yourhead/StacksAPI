---
name: Color
type: color
array: color-2, color-4
description: A color well for choosing colors.
value: HTML Color String
available: 2
generics: true
properties:
  - title: Prefix
    key: prefix
    type: string
    default: #
    markdown: yes

  - title: Default Value
    key: default
    type: HTML Color String
    default: #000000 Black
    description: The color the color well will be set to by default. If no color is provided Black will be used

---

A color well. 

When clicked the RapidWeaver shared color pallet is displayed. The selected color is converted to RGB and returned as a hex string.



{% include newstuff.html %}
### Color Array

Color controls can be used in arrays.  Each has its own subtitle and default, all other values are shared.  Color array types are:

- `color` : a regular color control.
- `color-2` : two color controls.
- `color-4` : four color controls.
