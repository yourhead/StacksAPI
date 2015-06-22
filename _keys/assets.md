---
name: Asset Files 
key: assets
type: array
group: content
value: An array of asset dictionaries.
description: Declare your static assets files here.
available: 2

links:
  - top: /plist
  - plist: assets

---

An array of asset files declarations. 

[Detailed Asset File Reference]({{ site.baseurl}}/plist/assets)

A stack may include other files and folders that to be exported. Each asset will be exported as-is, without templating, HTML conversion, or image optimization. Folders will be exported with all of their files (there is no need to declare each file within the folder). Each item in the array corresponds to a file and is a dictionary. See the asset dictionary page for more info.

> Note: It's up to you to ensure that the items have acceptable web-friendly naming and do not conflict with other files that might be present in other elements.