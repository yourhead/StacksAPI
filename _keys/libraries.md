---
name: Library Declarations
key: libraries
type: Array
value: An array of library dictionaries.
description: Declare your libraries here.
group: content
available: 5

links:
  - top: /plist
  - plist: keys/assets
  - plist: keys/templates

---

An array of library dictionaries.

#### Assets vs. Templates vs. Libraries

Assets, Templates, and Libraries are similar. Each can contain content and files to be published. But each imply different behavior and should be used differently.

##### Assets
Assets are NOT processed for templates. They are NOT included in edit-mode. Assets should be used whenever possible. They are simple and low-cost.
##### Libraries
Libraries are NOT processed for templates. Some libraries are included in edit-mode. Some libraries are built-in to stacks (e.g. jQuery and FontAwesome). Libraries are shared between all stacks on the site/page.  Use a library whenever you need to share common content between stacks.
##### Templates
Templates ARE processed for template variables. Some templates are included in edit-mode. Since templates must be processed you should include as few templates as possible -- move as much of your content to assets or libraries whenever you can.


#### Velocity Demo Stack
There is a complete example of using a custom library on GitHub: [Velocity Stack](https://github.com/yourhead/VelocityDemo).

#### Library Dictionary

Each line in the libraries array should be a dictionary. And each dictionary should represent a single library that should be called and/or published.

> Warning: Libraries are shared between all stacks. You should use caution and be a good developer citizen when choosing to include common libraries: check with other developers on the Stacks Slack Channel before including a popular library. If you include some code intended to be used by only your stacks, give the library an appropriatly unique name: e.g. `com.yourcompany.yourlibrary`

The library dictionary can include the following keys:

##### Name -- (required) -- key: `name`
The name of the library. This can be a custom name (see warning above) or the name of a built-in library: 
 - jQuery -- key: `jQuery` -- 1.8.3, 1.9.1, 1.10.2, 1.11.3, 1.12.4, 2.0.3, 2.1.4, 2.2.4, 3.0.0, 3.1.1
 - jQuery UI -- key: `jQueryUI` -- 1.11.4
 - FontAwesome -- key: `FontAwesome` -- 4.7.0
 - MooTools -- key: `MooTools` (deprecated, limited support) -- 1.4
 - VueJS -- key: `vuejs` (available: API v10) -- 2.3.4

Built-in libraries can be published with the site (this is the default) or linked from the most popular CDN (which differs for each library and is subject to change with the whims of the internet change). A CDN will only be used if the user opts-in to that feature using the Stacks preferences.

##### Filename -- (custom libraries only) -- key: `filename`
The name of a file containing the library content.

##### Scope -- (custom libraries only) -- key: `scope`  (in API v10)
If no scope is included, the scope defaults to `site`. Built-In libraries always publish in the site-scope. The scope can be any of the following:
	
	- `site` -- (default) -- The content of the custom library will be published to the Stacks common folder for the site and each page that uses the stack will include a CSS or JS reference to the file in the `<head>` of the page.
	- `page` -- The content will be included in the page's CSS or JS file. Page-scoped CSS libraries will be included in edit-mode.


##### Type -- (custom libraries only) -- key: `type`
The scope of a template determins where on the page/file it will be published, as well as which template variables will be processed. All custom libraries must include a type.

- `css` -- The each scope publishes content for each stack instance on the page. All tempalte variables will be processed.
- `js` -- The page scope publishes content ONLY ONCE for all stack instances on the page. Some template variables will be processed. Page-Scoped template variables will be processed, as well as any variable that is static for the entire page (e.g. version numbers and file-paths). Each template variable lists the scopes that it will be published in.

##### Minimum/Maximum Versions -- (jQuery only) -- key: `minVersion` and `maxVersion`
Stacks includes many versions of jQuery built in. If your stack is only compatible with specific versions, you should set the min/max such that your stack will always work.  Stacks will attempt to find the newest version of jQuery that works for the entire page.  Since that is not always possible, this is a best-effort attempt. In the cases when Stacks cannot find a compatible version, stacks with newer min/max versons will be prefered.

 > Warning: If your stack can work with any release of jQuery, DO NOT set any versions limits. A stack that supports a wider set will always work the best
