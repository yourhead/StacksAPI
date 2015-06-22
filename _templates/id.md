---
name: Stack Instance ID
syntax: "%id%"
group: properties and controls
description: The ID of the current stack.
available: 2



---



### Usage

```html
%id%
```


### Description

This keyword will be replaced by the HTML DOM id of inner element of the stack's wrapper divs. This is the id of the "stacks_in" element.

> Warning: Do not modify the CSS properties that the use sets such as border, margin, and padding. Doing so will confuse the user and may cause display inconsistencies in the Stacks edit mode user interface.


#### Example 1: used to limit the scope of CSS
adds a red border to all divs inside of your stack

```css
#%id% div {
    border: 1px solid red;
}
```
