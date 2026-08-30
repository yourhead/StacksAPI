---
title: Multi-line Text Input Control
name: Multi-line Text Input
description: A multi-line text input.
type: multi
value: string
available: 7
generics: yes
properties:

  - title: Default Value
    key: default
    type: string
    default: '""'
    description: When the stack is placed onto the page, the text field will be set to this value.

  - title: Clear Value
    key: clearValue
    type: string
    default: '""'
    description: When the user deletes all the text from the input, the control will automatically fill with this value. This is useful when a non-empty string is required.
    
---


A multi-line text entry. The string value is returned. 
Like all string value properties, you can retrieve an encoded value with escapes for specific languages (e.g., `%id=textInput -encodeJS%`).

The text inside a multi-line text input is very small. Please don't force users to type complex things here. Keep it simple.

### Size of the Control
Multi-line text inputs come in 2, 4, and 8 line sizes. There is no `multi` type without a size. If you need a one-line text entry, use the `input` control. Select the size by appending it to the type:

- `multi-2` : two-line text input.
- `multi-4` : four-line text input.
- `multi-8` : eight-line text input.



