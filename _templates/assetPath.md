---
name: Asset Path
syntax: "%assetPath%"
group: paths
description: The path to exported assets
available: 2

links:
  - plist: assets

---



### Usage

```html
%assetPath%
```

 - Replaced with the path to the asset export folder.


### Description

This template will be replaced by the path to Stacks' assets directory for the page. This will be needed to link to assets that have been included in plist.

 > Note: This path may different between edit/preview/publish modes.

[Detailed Asset File Reference]({{ site.baseurl}}/plist/assets)

#### Example 1: link to an included PDF document

```
<a href='%assetPath%/document.pdf' >Download PDF Document</a>
```






