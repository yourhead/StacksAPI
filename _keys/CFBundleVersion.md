---
name: Build Number
key: CFBundleVersion
humanReadableKey: Bundle version
type: string
description: The the current build number.
available: 2
group: version

links:
  - top: /plist

---

The build number of your stack. 

This should be a string with a number. The number should be simple integer value like "12345". It should increase with each release.

> Note: Any string may be used for the version number, but the increasing-integer format is required for automatic updating.
