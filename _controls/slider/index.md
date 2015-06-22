---
name: Slider
type: slider
group: numbers
description: A slider control for picking a number from a limited range.
value: number
available: 3
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

  - title: Ticks
    key: ticks
    type: number
    default: 0
    description: The number of tick marks to display on the slider. This includes the left and rightmost tick mark. Setting this value to 1 has undefined behavior.

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

A slider for choosing from a range of numbers. 

A slider always has a minimum and maximum value (defaults to 0 - 20). Tick marks can be displayed to help the user find specific values. The output value can be either an integer (if rounding is enabled) or a float.