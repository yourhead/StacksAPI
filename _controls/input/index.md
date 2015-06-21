---
name: Text Input
type: select
available: 1
properties:
  - title: ID
    key: id
    type: string
    required: true
    description: The ID for this control. This ID must be unique within this stack. The ID is used to refer to the control's property.  IDs should be alpha-numeric (dashes and underscores are allowed), but should not contain special characters.


  - title: Title
    key: title
    type: string
    default: '"Untitled"'
    required: true
    description: When the stack is placed onto the page, the default value will be used. If no default is provided, 0 will be used.

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
    default: No tooltip is displayed.
    description: The tooltip value is used to display hints for the user on the use of each control. If the function of the control is obvious, then a tooltip should be avoided. Simply re-displaying redundant information, like the title, has no value to the user.
    



---


A single line text entry. The string value is returned. 
Like all string value properties, you can retrieve an encoded value with escapes for specific languages (e.g., `%id=textInput -encodeJS%`).




