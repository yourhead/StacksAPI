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

This template is replaced by the path to Stacks' assets directory for the page. Use it to link to assets that have been included in the plist.

 > Note: This path may differ between edit/preview/publish modes.

[Detailed Asset File Reference]({% include docs-root.html %}/keys/assets)

#### Example 1: link to an included PDF document

```
<a href='%assetPath%/document.pdf' >Download PDF Document</a>
```




