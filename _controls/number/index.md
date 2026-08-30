---
name: Number
type: number
array: number-2, number-3, number-4
value: number
group: numbers
description: A number entry field, with a small up/down control for adjustment.
available: 8
generics: true
properties:
  - title: Minimum
    key: min
    type: number
    default: 0
    description: The minimum value for the slider.

  - title: Maximum
    key: max
    type: number
    default: 20
    description: The maximum value for the slider.

  - title: Rounding
    key: round
    type: Boolean
    default: True
    markdown: true

  - title: Units
    key: units
    type: string
    default: No units are displayed.
    description: The units string is displayed next to the number value. The units string is only for the user interface and will not be included in template output.

  - title: Default Value
    key: default
    type: number
    default: 0
    markdown: true

  - title: Clear Value
    key: clearValue
    type: string
    default: '""'
    description: When the user deletes all the text from the input, the control will automatically fill with this value. This is useful when a non-empty string is required.

    

---

A text entry field that only accepts numbers within an allowed range. Up/down arrows next to the field increment or decrement the number.


{% include newstuff.html %}
### Number Control Array

Number controls can be used in arrays. Each number control has its own subtitle and default; all other values are shared.

> NB: number-3 requires Stacks API v8 (Stacks v3.1+), 2 & 4 require v7 (Stacks v3.0+), single control requires v2.

Number control types are:

- `number` : a regular number control.
- `number-2` : two number controls.
- `number-3` : three number controls.
- `number-4` : four number controls.
