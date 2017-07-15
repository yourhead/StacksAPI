---
name: Template Files
key: templates
type: Array
value: An array of template dictionaries.
description: Declare your template files here.
group: content
available: 5

links:
  - top: /plist
  - plist: keys/assets
  - plist: keys/libraries

---

An array of template dictionaries.

#### Assets vs. Templates vs. Libraries

Assets, Templates, and Libraries are similar. Each can contain content and files to be published. But each imply different behavior and should be used differently.

##### Assets
Assets are NOT processed for templates. They are NOT included in edit-mode. Assets should be used whenever possible. They are simple and low-cost.
##### Libraries
Libraries are NOT processed for templates. Some libraries are included in edit-mode. Some libraries are built-in to stacks (e.g. jQuery and FontAwesome). Libraries are shared between all stacks on the site/page.  Use a library whenever you need to share common content between stacks.
##### Templates
Templates ARE processed for template variables. Some templates are included in edit-mode. Since templates must be processed you should include as few templates as possible -- move as much of your content to assets or libraries whenever you can.


#### Template Dictionary

Each line in the templates array should be a dictionary. And each dictionary should represent a single template file that should be processed.

> Each template file and each tempalte variable within each file adds a significant performance cost to your stack. To ensure your stack has the best peformance strive to include as few template files as possible with as few templates variables as possible.

The template dictionary can include the following keys:

##### Filename -- key: `filename`
The filename of the template. Do not include the path to the file.

##### File type -- key: `type`
This can be any of the following:
	
	- `html` -- This content is included in the index.html page content. You can choose where on the page the content will be included using the scope (see below). `html` content is included in Edit, Preview, and Publish modes.
	- `css` -- The style content for your stack. It will be grouped with other style content and published in a separate file.
	- `js` -- Javascript content is NOT included in edit mode. By default JS content is wrapped in a closure and grouped together into a single JS file.
	- `php` -- PHP is only included when publishing. It is NOT combined into a single file, but published in individual files.
	- `file` -- The file-type template is a catch-all. You should use it only when one of the other template types doesn't fit. (Example: JSON Config files, Raw Text files, etc.) File type content can be any sort of UTF-8 text based file that can be template processed (if you'd like to include non-template processed files, or non-text files, they should be [assets](/keys/assets) instead). Keep in mind that each file will be processed for templates. Include only what you need. Use assets for all that you can.

##### Scope -- key: `scope`
The scope of a template determins where on the page/file it will be published, as well as which template variables will be processed.

- `each` -- *default* -- The each scope publishes content for each stack instance on the page. All tempalte variables will be processed.
- `page` -- The page scope publishes content ONLY ONCE for all stack instances on the page. Some template variables will be processed. Page-Scoped template variables will be processed, as well as any variable that is static for the entire page (e.g. version numbers and file-paths). Each template variable lists the scopes that it will be published in.

###### Limited Scopes -- These scopes are limited to specific types of content

- `site` -- (CSS only) Like the page scope, the site scope will only be published once for the entire site.
- `pageHeadAbove` -- (HTML only) -- HTML content, in the page scope, positioned in the `<head>` tag above all other content, it will be immediately AFTER the call to jQuery, jQueryUI, and FontAwesome within the head tag of the page.
- `pageHeadBelow` -- (HTML only) -- HTML content, in the page scope, positioned in the `<head>` tag below all js declarations.
- `pageBodyAbove` -- (HTML only) -- HTML content, in the page scope. The content of this template will be placed immediately BEFORE all other stack content. This is the absolute highest place in the `<body>` tag that Stacks has access to in the RapidWeaver API. 
- `pageBodyBelow` -- (HTML only) -- HTML content, in the page scope. The content of this template will be placed immediately AFTER all other stack content. This is the absolute lowest place in the `<body>` tag that Stacks has access to in the RapidWeaver API. Some Javascript works best that way.