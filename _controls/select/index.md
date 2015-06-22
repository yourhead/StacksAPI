---
name: Popup Menu
type: select
description: A Popup menu to for choosing from a list of items.
available: 3
generics: yes
properties:

  - title: Menu Items
    key: items
    type: Array of menu item dictionaries
    required: true
    markdown: true

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

    

---

A popup menu for selecting a single item from a short list. 
Popup menus are a good way to choose from a short list of items. If there are only two items in the list a [checkbox](../checkbox) is probably more appropriate. If the list of items is long (more than 15 or so) then it may be more appropriate to just ask the user to type in the value in a [Text Input](../input) field.