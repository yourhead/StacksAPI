---
title: The Stacks Bundle
layout: page
back:
  - top: /
links:
  - top: /plist
  - top: /templates

---

Overview
Each stack stack is a bundled folder. The folder contains all the template files, assets, and a property list that defines how the stack will behave.

### The Bundle Structure
The bundle of a stack follows the standard Mac OS X bundle structure. It looks like this:

- MyStackName.stack - the folder for the stack.
  - Contents - all bundles store their contents in a Contents folder.
    - [Info.plist]({{ site.baseurl }}/plist) - the bundle property-list that describes the stack. This will define all of the properties, templates, and assets your stack uses.
    - [Resources]({{ site.baseurl }}/resources) - all of the templates and assets your stack uses will be stored here.
      - icon@50.png - a 50px icon file that will be used in the grid view of the Stacks library
      - icon@58.png - a 58px icon file that will be used in the detail view of the Stacks library
      - [template.html]({{ site.baseurl }}/templates) - a stack may contain many template files for HTML, CSS, JS, etc., but it must contain at least one HTML tempalate.
      - assetfile.xxx - a stack may contain many asset files. Each asset will be exported with the Stacks page when the site is published.
      - assetfolder - a stack may contain an asset folder. All the hierarchical contents of the folder will be exported with the Stacks page when the site is published.

### The Property List — Info.plist
All of the properties that will be used for your stack are stored in the Info.plist file. You can learn more about it in the Info.plist document.


### Resources
All of the files (other than the Info.plist) used by your stack should be stored inside the Rsources folder. This includes all of the templates, assets, and anything else your stack requires.

Note: You can place a complete stack bundle inside the Resources folder of another stack. This allows a number of related stacks to be installed from a single Finder icon.