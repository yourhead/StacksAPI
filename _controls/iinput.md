---
name: Text Input
type: select
available: 1
propertiess:
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
    description: Hide or show this control based on the value of another control. Enables allow a stack to show only the controls needed by the user to achieve a specific task.<br>The enable dictionary defines the ID of another control and the value that other control must equal. When the other control's value is not equal to the value defined here, this control (Text Input) is hidden.



---

A single line text entry. The string value is returned. 
Like all string value properties, you can retrieve an encoded value with escapes for specific languages (e.g., `%id=textInput -encodeJS%`).

