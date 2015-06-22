---
name: ID
key: CFBundleIdentifier
humanReadableKey: Bundle Identifier
type: string
description: The unique ID for your stack.
required: yes

links:
  - top: /plist

---

The ID is the unique identifier for your stack. To ensure unqueness, it's recommended you use [reverse DNS format](http://en.wikipedia.org/wiki/Reverse-DNS). 
This should be a string consisting of just lowercase characters, periods, and underscores. ***There should be no spaces in the ID.*** It must uniquely identify your stack.

> Note: This value is used to bind the user's content to your stack. For this reason ***the ID must never change.***