---
name: Asset Files
key: assets
type: Array
group: content
value: An array of asset dictionaries.
description: Declare your static assets files here.
available: 2

links:
  - top: /plist
  - plist: keys/templates
  - plist: keys/libraries

---

An array of asset files declarations.

Each line in the assets array should be a dictionary. And each dictionary should represent an asset file/folder to be published.

#### Assets vs. Templates vs. Libraries

Assets, Templates, and Libraries are similar. Each can contain content and files to be published. But each imply different behavior and should be used differently.

##### Assets
Assets are NOT processed for templates. They are NOT included in edit-mode. Assets should be used whenever possible. They are simple and low-cost.
##### Libraries
Libraries are NOT processed for templates. Some libraries are included in edit-mode. Some libraries are built-in to stacks (e.g. jQuery and FontAwesome). Libraries are shared between all stacks on the site/page.  Use a library whenever you need to share common content between stacks.
##### Templates
Templates ARE processed for template variables. Some templates are included in edit-mode. Since templates must be processed you should include as few templates as possible -- move as much of your content to assets or libraries whenever you can.



 #### Asset Dictionary

The asset dictionary can include the following keys:

##### Filename -- key: `filename`
The filename of the asset. Do not include the path to the file.

> Note: The filename can refer to an entire folder. All content inside the folder will be published.

##### Scope -- key: `siteAsset` (Boolean -- defaults to NO)
Normal assets are published, along with the page. Site assets are just once for the whole site and shared among all pages. They are published to the Stacks common directory for the site. To refer to the them you should use the [`%siteAssetPath%`](/templates/siteAssetPath) template variable

> Note: It's up to you to ensure that the items have acceptable web-friendly naming and do not conflict with other files that might be present in other elements.
