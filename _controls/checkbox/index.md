---
name: Checkbox
type: checkbox
array: checkbox-2, checkbox-3, checkbox-4
description: A simple checkbox for enabling/disabling properties.
value: any value
available: 8
generics: true

properties:
  - title: Radio Buttons
    key: radio
    type: boolean
    default: False
    description: Radio buttons will allow only one button in the group to be pushed.

  - title: True Value
    key: trueValue
    type: string
    default: True
    description: When the checkbox is checked this value will be used in replacement templates. In arrays, this may be an arrof of strings.

  - title: False Value
    key: falseValue
    type: string
    default: False
    description: When the checkbox is unchecked this value will be used in replacement templates. In arrays, this may be an arrof of strings.

  - title: Default Value
    key: default
    type: boolean
    default: False (not pushed in)
    description: When this stack is placed on a page the default value will be used. The default value should be either the true or false values.


---

A checkbox for enabling or selecting from two options. 

Although a checkbox would seem to return a boolean value, for historical reasons a checkbox control is able to return any value type. This means, by using the True Value and False Value properties a checkbox can return the string "Jedi" if checked and the value "Sith" when unchecked, or integers, floats, or booleans.


### Radio Mode

Checkboxes arrays can be used where only one of the group is allowed to be checked at a time.  To use checkboxes in this mode use one of the array types (see below) and enable the Radio property.


{% include newstuff.html %}
### Checkbox Array

Checkboxes can be used in arrays.  Each has its own subtitle, trueValue, falseValue, and default, all other values are shared.

> NB: checkbox-3 and trueValue/falseValue arrays requires Stacks API v8 (Stacks v3.1+), 2 & 4 require v7 (Stacks v3.0+), single control requires v1.

Checkbox types are:

- `checkbox` : a regular checkbox.
- `checkbox-2` : two checkboxes.
- `checkbox-3` : three checkboxes.
- `checkbox-4` : four checkboxes.
