---
name: Stack Container
syntax: "%slice%"
description: A container for other stacks.
available: 10

---



### Usage

```html
%slice%
```

or

```
%slice -addTypes="<stack_id_1>, <stack_id_2>" -allowedTypes="<stack_id_1>, <stack_id_2>" -addInit=<n>%
```

also

```
%slice -maxChildren=<n>%
```


> -addTypes, -allowedTypes, and -addInit were introduced in API v7.

> Containers were introduced in API v1.


### Description

A generic stack container (the Drop Stacks Here). This is the core of the One Column stack.

#### Add Types
Slice accepts properties that define how the slice container will behave.  These properties can alone, but they are designed to be used together.  See the open source [Image Fun](https://github.com/yourhead/ImageFunStack) stack on GitHub for a complete detailed example of these properties.

- **Add Types** - `addTypes` - This will add a + (plus) button to the UI of the stack.  When the user presses the button a new stack of the specified ID will be added to the container.  This encourages (but does not limit) the user to use a specific type of stack with this container.

- **Allowed Types** - `allowedTypes` - Allowed types will limit which types may be dragged in to a container. If allowedTypes is not present, then all stacks are allowed. *Note: Specifying a stack `addTypes` that is not also in `allowedTypes` has undefined behavior.*

- **Initial Added** - `addInit` - A container can begin with a number of stacks pre-added.  This should only be used in conjunction with addTypes and only when there is a single type.

- **Max Children** - `maxChildren` - You can limit the number of children that can be added. One the container has the maximum number of items it will prevent dragging new items in and will remove the + button.
