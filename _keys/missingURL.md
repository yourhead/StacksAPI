---
name: Missing URL
key: missingURL
type: String
group: URLs
description: A URL for the user to download a missing stack
available: 10

---

The URL for users to be directed to when this stack becomes uninstalled.

This should NOT be an automatic download unless the stack was free. It should be a place to go to re-download a stack by a registered user. This could be your support URL if that is the only way to re-download a purchased stack.

> If no URL is provided then the user will be directed to the [Info URL](../infoURL). If the Info URL is also absent, then the user will be directed to the [Help URL](../helpURL). If both the Info URL and the Help URL are absent then the user will be directed to the RapidWeaver Community website.
