---
name: Details Button
type: detail
description: A toggle for showing more detailed controls.
value: Boolean
available: 7

properties:

  - title: Default Value
    key: default
    type: boolean
    default: False (not pushed in)
    description: The value of the details button when it's the stack is placed on the page.

  - title: ID
    key: id
    type: string
    required: true
    generic-markdown: true

  - title: Tool Tip
    key: toolTip
    type: string
    generic-markdown: true
    default: No tooltip is displayed.


---

A toggle button specifically for showing more details. It behaves exactly like a checkbox (and it's value **can** be used in template variables just like a checkbox) but it has a UI that is simple. It does not display a title, but does have a tooltip for explanation.

