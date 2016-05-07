---
name: Color
type: color
array: color-2, color-3, color-4
description: A color well for choosing colors.
value: HTML Color String
available: 8
generics: true
properties:

  - title: Opacity Enable
    key: allowsOpacity
    type: boolean
    default: no
    description: Enable the opacity slider on the color selection box.

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

When clicked the RapidWeaver shared color pallet is displayed. The selected color is converted to RGB and returned as a hex string or rgba color value.

### Opacity
The color control now allows you to enable opacity when selecting colors.  To ensure backward compatability it defaults to being disabled.

Colors that include an opacity will be output (in templates) as rgba color values.  Colors without an opacity will be output as HTML hex colors.


### Specifying defaults
Default values can be supplied for color controls useing HTML hex values, rgb values, or rgba values.  Rgb and rgba color components can use 0-255 (rgb values equivalent to the HTML hex value) or percentages `0%` - `100%`.  The opacity component in rgba can use either percentages `0%` - `100%` or decimal notation `0.0` - `1.0`

An HTML hex color for red:

```
#FF0000
```

An rgb color for green:

```
rgb(0, 255, 0)
```

An rgba color for translucent blue:

```
rgba(0, 0, 50%, 0.5)
```


{% include newstuff.html %}
### Color Array

Color controls can be used in arrays.  Each has its own subtitle and default, all other values are shared.

> NB: color-3 requires Stacks API v8 (Stacks v3.1+), 2 & 4 require v7 (Stacks v3.0+), single control requires v1.

Color array types are:

- `color` : a regular color control.
- `color-2` : two color controls.
- `color-3` : three color controls.
- `color-4` : four color controls.

In arrayed color controls default values for the `default` key can either be a single color (applied to all controls in the array) or an array of colors.
