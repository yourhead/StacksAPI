---
name: Number
type: number
array: number-2, number-4
value: number
group: numbers
description: A number entry field, with a small up/down control for adjustment.
available: 2
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
    key: rounding
    type: Boolean
    default: True
    markdown: true

  - title: Units
    key: units
    type: string
    default: No units are displayed.
    description: The units string is displayed next to the slider value. The units is strictly for the user interface, it will not be included in template output value.

  - title: Default Value
    key: default
    type: string
    default: The first menu item.
    markdown: true

  - title: Clear Value
    key: clearValue
    type: string
    default: '""'
    description: When all the content is cleared out of a text input area (the user deletes all the text), the control will automatically fill with this value. This is useful for applications where a non-empty string is required.

    

---

A text entry field that validates only numbers in an allowed range. There are up/down arrows next to text entry to increment/decrement the number.


{% include newstuff.html %}
### Number Control Array

Number controls can be used in arrays.  Each has its own subtitle and default, all other values are shared.  Number control types are:

- `number` : a regular number control.
- `number-2` : two number controls.
- `number-4` : four number controls.
