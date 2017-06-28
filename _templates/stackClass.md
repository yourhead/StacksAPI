---
name: Stack Class
syntax: "%stackClass%"
group: properties and controls
description: The class added to a stack
available: 10

---



### Usage

```html
%stackClass%
```


### Description

Every custom stack has a specific class added to the inner wrapper div. the class is created using the stack's ID, but but has some small changes made to avoid characters that are not permitted inside a class (e.g. '.' is replaced with an underscore).

This class is useful for isolating your CSS to apply specifically to your stack.

> This template is applied in the pre-processor and has very low performance cost.
