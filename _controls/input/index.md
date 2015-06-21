---
title: Text Input Control
name: Text Input
type: input
value: string
available: 1
properties:
  - title: ID
    key: id
    type: string
    required: true
    generic-markdown: true

  - title: Title
    key: title
    type: string
    default: '"Untitled"'
    required: true
    generic-markdown: true

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

  - title: Enable
    key: enable
    type: dictionary
    default: enabled
    generic-markdown: true

  - title: Tool Tip
    key: toolTip
    type: string
    generic-markdown: true
    default: No tooltip is displayed.
    



---


A single line text entry. The string value is returned. 
Like all string value properties, you can retrieve an encoded value with escapes for specific languages (e.g., `%id=textInput -encodeJS%`).




