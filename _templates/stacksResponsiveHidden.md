---
name: Hidden Responsive 
syntax: "%id=stacksResponsiveHidden[0]%"
group: properties and controls
description: Responsive user controls for hiding stacks.
available: 7

---



### Usage

```html
%id=stacksResponsiveHidden[<size_index>]%
```

 - `<size_index>` - The size of the device.
   - `0` : Mobile
   - `1` : Tablet
   - `2` : Desktop



### Description

This is the output from one of the built-in controls that is part of the Stacks UI for every stack (except inline stacks which have no default controls).  It allows the user to hide any stack on specific devices.  Stacks does this by simply adding `display: none;` to the CSS of the stack in the appropriate media query.

Your stack can use these values to change in any way that you like.

This is useful when your stack creates element via JS that are injected on other parts of the page. You may want to disable the display of those elements to ensure the user gets their desired behavior.


