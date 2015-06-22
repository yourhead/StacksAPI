---
name: Color
type: color
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

  - title: Clear Value
    key: clearValue
    type: string
    default: '""'
    description: When all the content is cleared out of a text input area (the user deletes all the text), the control will automatically fill with this value. This is useful for applications where a non-empty string is required.

    

---

A color well. 

When clicked the RapidWeaver shared color pallet is displayed. The selected color is converted to RGB and returned as a hex string.