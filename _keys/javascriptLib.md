---
name: Javascript Library
key: javascriptLib
type: String
description: Load a JS library.
group: javascript
available: 2

links:
  - top: /plist

---

The Javascript base library to be included for the page. 
Stacks will include a Javascript base library for all the stacks to share. There are three supported libraries:

 * jQuery
 * MooTools
 * jQuery UI *(Available: Stacks API v3)*

The library will be included by using the Google AJAX Libraries API. This is a convenient and reliable source of the most recently released versions of the libraries. However it does come with some important implications: