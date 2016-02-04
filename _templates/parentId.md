---
name: Parent ID
syntax: "%parentId%"
group: properties and controls
description: The ID parent stack of the current stack.
available: 7



---



### Usage

```html
%parentId%
```


### Description

All stacks, when placed onto the page, are inside of a parent stack.  This template gives you the ID of that parent stack.

When the parent stack is the page itself, then this will be replaced with the empty string `""`;
