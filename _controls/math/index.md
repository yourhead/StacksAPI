---
name: Math
type: math
group: numbers
description: Perform basic calculations in your controls.
value: number
available: 2
properties:

  - title: Argument 1
    key: arg1
    type: number or string
    required: yes
    description: Arguments come in two formats. They can either be a constant number or a string that specifies the ID of some other control. If taking the value from another control, the other control must return a number typed value.

  - title: Argument 2
    key: arg2
    type: number or string
    required: yes
    description: Arguments come in two formats. They can either be a constant number or a string that specifies the ID of some other control. If taking the value from another control, the other control must return a number typed value.

  - title: Operator
    key: operator
    type: string, on of
    required: yes
    description: Operators have the standard C language functions.

  - title: Rounding
    key: round
    type: Boolean
    default: True
    markdown: yes

---

A slider for choosing from a range of numbers. 

A slider always has a minimum and maximum value (defaults to 0 - 20). Tick marks can be displayed to help the user find specific values. The output value can be either an integer (if rounding is enabled) or a float.