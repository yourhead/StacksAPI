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

A virtual control to perform simple math. 
Most functions that math-controls provide can be more easily performed using template expressions. However, there are still a few ways that math-controls are useful, mostly in enable logic.

Math properties follow a two-argument, one-operator format: 
<argument_1> <operator> <argument_2> = <result>

