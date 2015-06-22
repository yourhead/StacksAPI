---
name: Site Asset Path
syntax: "%siteAssetPath%"
group: paths
description: The path to assets shared site-wide
available: 2

links:
  - plist: assets

---



### Usage

```html
%siteAssetPath%
```



### Description

Returns the path to the assets directory shared by all pages of the site. This will be needed to link to assets that have been included as site assets.

 > Note: This path may different between edit/preview/publish modes.

[Detailed Asset File Reference]({{ site.baseurl}}/plist/assets)


#### Example 1: link to an included PDF document

```
<a href='%siteAssetPath%/document.pdf' >Download PDF Document</a>
```






