---
name: Group
key: group
type: string
description: The library group for your stack.
available: 3
---

Note:  Group is provided only for compatibility.  Tags are preferred.  This key is superseded by the Tags key.  If your stack uses tags, then the group will be ignored.

The library group for your stack.  

Stacks libraries are organized into groups. You can specify the group your stack should be placed in by adding the group property. A stack without a group will be placed into the "Other Stacks".