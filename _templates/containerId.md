---
name: Container ID
syntax: "%containerId%"
group: properties and controls
description: The ID container of the current stack.
available: 7



---



### Usage

```html
%containerId%
```


### Description

All stacks, when placed onto the page, are inside of a container node (which is just a `%slice%`).  This template gives you the ID of that container node.

When the container is the page itself, then this will be replaced with the empty string `""`;
