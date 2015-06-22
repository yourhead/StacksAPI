---
name: Sparkle Appcast URL
key: SUFeedURL
type: string
description: The Appcast URL for updates.
available: 2
group: URLs

links:
  - top: /plist

---

The URL used by the Sparkle automatic updater to locate the stack's update appcast. 

You can provide a URL to an XML appcast on your own server. The appcast will be read and compared to the version information in the currently installed stack. If the appcast version is newer, then the appcast info will be used to install the new version. 

You can find more information about creating an appcast and publishing an update on the [Sparkle website](http://wiki.github.com/andymatuschak/Sparkle/publishing-an-update).

> Note: Setting up an appcast for the first time can be challenging. There are many details required before it all begins to work. Stacks will output some information about update failures to the developer log. If you need help getting things set up please post of the [Stack Developers Group](http://groups.google.com/group/stack_developers?hl=en) with details and questions. Others have been through the process and can offer some assistance.

