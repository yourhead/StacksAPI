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

When the preprocessor is enabled mode-conditional templates may *not* be nested and have a new format:

> Example:  `%%[if edit]%%`

The new format adds a percent sign.