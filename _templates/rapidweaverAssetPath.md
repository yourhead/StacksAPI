---
name: RapidWeaver Asset Path
syntax: "%rapidweaverAssetPath%"
group: paths
description: The path to exported RapidWeaver assets
available: 2
  
links:
  - plist: assets

---



### Usage

```html
%rapidweaverAssetPath%
```

 - Replaced with the path to the asset RapidWeaver export folder.


### Description

Returns the the path to the RapidWeaver Assets directory (note: this was known as the Resources directory up until RapidWeaver v5). This will be needed to link to assets that the user has included in the Page Inspector window in RapidWeaver.

**This is not the assetPath.**

> Note: There is no way for Stacks your stack to export files to this folder.  This folder is for the user's content only. The path gives you access to it.  

> Warning: This path will not exist in Edit mode. And may be different between Preview/Publish.





