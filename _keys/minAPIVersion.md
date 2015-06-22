---
name: Minimum Stacks API Version
key: minAPIVersion
type: number
group: version
description: The minimum API version.

links:
  - top: /plist

---

The minimum API version required by your stack. 
You can use the minimum version to detect a specific version of the API that your stack requires. Values should be a simple integer of the major version number required. If you are using the Stacks API 2.0 features, you should set the minAPIVersion to 2.

> Warning: Only use a min API version if there is a known incompatibility. Do not blindly add min limits.

