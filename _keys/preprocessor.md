---
name: Preprocessor
key: preprocessor
type: Boolean
description: Enable Stacks 3.5 preprocessor
required: no
group: content
available: 10

links:
  - top: /plist

---


To enable the Stacks 3.5 preprocessor and disable old-style preprocssor set this key to YES.  It is strongly recommended that you use enable the new preprocessor as it is significantly faster.


When the preprocessor is enabled [conditional mode macros]({{ site.baseurl}}/templates/display) will have a new format and may *not* be nested.

> Example:  `%%[if edit]%%`

The new format adds a percent sign.