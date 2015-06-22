---
name: Template Files
key: templates
type: array
value: An array of template dictionaries.
description: Declare your template files here.
group: content
available: 5

links:
  - top: /plist
  - plist: templates

---

An array of template file declarations. 

[Detailed Template Dictionary Reference]({{ site.baseurl}}/plist/templates)

Each entry in the Templates array is a dictionary that corresponds to a template file for your stack. When the page is published each template in your stack is processed, each template variable within the template is replaced with the content or property for each stack. 
