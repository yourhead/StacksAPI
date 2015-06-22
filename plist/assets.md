---
title: Asset Files Dictionary
layout: page
back:
  - top: /plist
---

### Overview
Assets are files that your stack needs to be published.  Unlike templates, assets are published as-is without any changes.

Each asset must be declared in the Info.plist inside the assets array. Each item in the array is a dictionary that defines the filename and if the asset is a site-asset.

To access your assets you should use the [Asset Path](/template-variables/#AssetPath) template variable along with the file name of your asset.

To access your assets that have the Site Asset property enabled, you should use the [Site Asset Path](/template-variables/#SiteAssetPath) template variable along with the file name of your asset.




### Contents

##### Basic
  * [File Name][] — *filename (required)*
  * [Site Asset][] — *siteAsset*







### Reference

___
[File Name]: #filename
<a name='filename'></a>
####File Name *— filename*
 * *Key* <br> filename
 * *Type* <br> String
 * *Required*

#####Description
The file name of asset. This should be only the name, not the complete path.



___
[Site Asset]: #SiteAsset
<a name='SiteAsset'></a>
####Site Asset *— siteAsset*
 * *Key* <br> siteAsset
 * *Type* <br> Boolean

#####Description
When the siteAsset boolean is set to true, then the asset will be published to the site assets directory (usually rw_common).  You can access these by using the [Site Asset Path](/template-variables/#SiteAssetPath) template variable.






