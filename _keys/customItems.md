---
name: Controls
key: customItems
type: array
value: An array of control dictionaries.
group: content
description: The Info sidebar controls.
available: 2

links:
  - top: /plist
  - plist: controls

---

An array of custom property declarations. 

[Detailed Controls Reference]({{ site.baseurl}}/plist/controls)

Each item in the custom properties array defines a property that you stack can use in its templates. Most custom properties have a corresponding GUI control for the user to set the property. When a stack in the layout is selected, the GUI controls for each custom properties are shown in the sidebar. As the user changes the values, the template files for your stack are injected with the new values. 

