---
name: Popup Menu
type: select
available: 3
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
    description: The title displayed next to the control. Long titles will be truncated, so keep it short.

  - title: Default Value
    key: default
    type: string
    default: The first menu item.
    markdown: true

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

  - title: Menu Items
    key: items
    type: Array of menu item dictionaries
    required: true
    markdown: true

  - title: Tool Tip
    key: toolTip
    type: string
    default: No tooltip is displayed.
    description: The tooltip value is used to display hints for the user on the use of each control. If the function of the control is obvious, then a tooltip should be avoided. Simply re-displaying redundant information, like the title, has no value to the user.
    

---

A popup menu for selecting a single item from a short list. 
Popup menus are a good way to choose from a short list of items. If there are only two items in the list a [checkbox](../checkbox) is probably more appropriate. If the list of items is long (more than 15 or so) then it may be more appropriate to just ask the user to type in the value in a [Text Input](../input) field.