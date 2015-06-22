---
name: Checkbox
type: checkbox
path: wow
description: A simple checkbox for enabling/disabling properties.
value: any value
available: 1
generics: true

properties:
  - title: True Value
    key: min
    type: number
    default: 0
    description: When the checkbox is checked this value will be used in replacement templates.

  - title: False Value
    key: max
    type: number
    default: 20
    description: When the checkbox is unchecked this value will be used in replacement templates.

  - title: Default Value
    key: default
    type: string
    default: The first menu item.
    description: When this stack is placed on a page the default value will be used. The default value should be either the true or false values.

  - title: Clear Value
    key: clearValue
    type: string
    default: '""'
    description: When all the content is cleared out of a text input area (the user deletes all the text), the control will automatically fill with this value. This is useful for applications where a non-empty string is required.



---

A checkbox for enabling or selecting from two options. 

Although a checkbox would seem to return a boolean value, for historical reasons a checkbox control is able to return any value type. This means, by using the True Value and False Value properties a checkbox can return the string "Jedi" if checked and the value "Sith" when unchecked, or integers, floats, or booleans.