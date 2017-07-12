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

 > NB: By opting in to the new-style preprocessor, removes support for all deprecated API.


When the preprocessor is enabled [conditional mode macros]({{ site.baseurl}}/templates/display) will have a new format and may *not* be nested.

> Example:  `%%[[if edit]]%%`

The new format doubles the percent signs and square-brackets.