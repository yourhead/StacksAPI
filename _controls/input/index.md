---
title: Text Input Control
name: Text Input
description: A simple text input.
type: input
array: input-2, input-4
value: string
available: 1
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
    description: When all the content is cleared out of a text input area (the user deletes all the text), the control will automatically fill with this value. This is useful for applications where a non-empty string is required.
    
---


A single line text entry. The string value is returned. 
Like all string value properties, you can retrieve an encoded value with escapes for specific languages (e.g., `%id=textInput -encodeJS%`).



{% include newstuff.html %}
### Text Input Array

Text Input can be used in arrays.  Each has its own subtitle and default, all other values are shared.  Text Input array types are:

- `input` : a regular text input.
- `input-2` : two text input.
- `input-4` : four text input.



