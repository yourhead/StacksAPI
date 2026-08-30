---
title: Text Input Control
name: Text Input
description: A simple text input.
type: input
array: input-2, input-3, input-4
value: string
available: 8
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


A single line text entry. The string value is returned. 
Like all string value properties, you can retrieve an encoded value with escapes for specific languages (e.g., `%id=textInput -encodeJS%`).



{% include newstuff.html %}
### Text Input Array

Text Input can be used in arrays. Each input has its own subtitle and default; all other values are shared.

> NB: input-3 requires Stacks API v8 (Stacks v3.1+), 2 & 4 require v7 (Stacks v3.0+), single control requires v1.

Text Input array types are:

- `input` : a regular text input.
- `input-2` : two text inputs.
- `input-3` : three text inputs.
- `input-4` : four text inputs.


