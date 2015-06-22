---
title: Template Files Dictionary
layout: page
back:
  - top: /plist
---


### Overview
All of the template files that your stack uses must be declared in the Info.plist inside the templates array. Each item in the array is a dictionary that defines the name, type, and scope of the template.





### Contents

##### Basic
  * [File Name][] — *filename (required)*
  * [Type][] — *type (required)*
  * [Scope][] — *scope*







### Reference

___
[File Name]: #filename
<a name='filename'></a>
####File Name *— filename*
 * *Key* <br> filename
 * *Type* <br> String
 * *Required*

#####Description
The file name of template. This should be only the name, not the complete path.



___
[Type]: #type
<a name='type'></a>
####Type *— type*
 * *Key* <br> type
 * *Type* <br> String
 * *Required*

#####Description
The type of template.  This must be one of: `html`, `css`, `js`, `php`, or `file`.



___
[Scope]: #scope
<a name='scope'></a>
####Scope *— scope*
 * *Key* <br> scope
 * *Type* <br> String, either `each` or `page`
 * *Default* <br> `each`
 * *Optional*

#####Description
The scope of the template defines how the template will be added to the page.

  * each — Templates with the each scope are added to the page once fore each instance of a stack on the page and in the order that the stack instances appear on the page.
  * page — Templates with the page scope are added to the page only once, no matter how many instances of a stack are on the page. All of the page scoped templates precede any each scoped templates.
  
##### HTML Page Scope
Page scoped HTML templates will be place in the &lt;head> tag of the page following the CSS and JS links. This is useful for including links to external CSS and libraries.  
Just as in each scoped templates, CSS is included in Edit Mode but Javascript will be disabled.
**Use the feature sparingly as linking to external resources can slow down page loads**

> Note: For improved performance disable external CSS links in Edit Mode.

##### CSS Page Scope
Page scope CSS templates will be added to the pages CSS file and will preceed the each scoped CSS.  This allows you to define the base styes once for all stack instances in the page scope and override the styles when necessary in the each scoped templates.

##### Javascript Page Scope
Page scoped Javascript is included in its own closure separate from the closure for the each scoped Javascript. This allows you to define Javascript functions once for all instances of the stack on the page which will speed up the page and reduce the memory footprint.

##### PHP Page Scope
Page scoped PHP will be included in the linked php. It will preceed the each scoped PHP.

___
### File templates

#### Assets are faster than templates
Most files that are exported with the page should be added as an asset. Assets are included without any sort of template processing so there is no performance penalty for adding them.

#### Templates are processed
There are times when it is helpful to inject properties from your stack into included files. You can add a template with the type of `file` for this purpse. File templates can be any text file (UTF-8).

#### Not for edit mode
Because template files may be very slow to process, they will not be processed for edit mode.  Only HTML and CSS templates are processed for edit mode.








