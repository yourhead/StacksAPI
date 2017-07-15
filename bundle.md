---
title: The Stacks Bundle
layout: page
back:
  - top: /
links:
  - top: /plist
  - top: /templates
  - plist: keys/assets
  - plist: keys/libraries
  - plist: keys/templates

---

Overview
Each stack stack is a bundled folder. The folder contains all the template files, assets, and a property list that defines how the stack will behave.

### The Bundle Structure
The bundle of a stack follows the standard Mac OS X bundle structure. It looks like this:

- MyStackName.stack - the folder for the stack.
  - Contents - all bundles store their contents in a Contents folder. Blame Apple. I didn't invent this. ;-) 
    - [Info.plist](/plist) - the bundle property-list that describes the stack. This will define all of the properties, templates, and assets your stack uses.
    - Resources - all of the templates, libraries, and assets your stack uses are stored here.
      - `large_<icon-name>.png` - a large-mode Stacks library icon for non-retina screens (64px x 64px) [The `<icon-name>` is defined in the plist.](/keys/icon)
      - `large_<icon-name>@2x.png` - a large-mode Stacks library icon for retina screens (128px x 128px)
      - `medium_<icon-name>.png` - a medium-mode Stacks library icon for non-retina screens (32px x 32px)
      - `medium_<icon-name>@2x.png` - a medium-mode Stacks library icon for retina screens (64px x 64px)
      - `small_<icon-name>.png` - a a small-mode Stacks library icon for non-retina screens (16px x 16px)
      - `small_<icon-name>@2x.png` - a small-mode Stacks library icon for retina screens (32px x 32px)
      - [`<asset_files>` or `<asset_folders>` (link) ](/keys/assets/) - asset files will be published with your stack. assets are NOT template processed. you can include any number of assets. they can be any type of file. assets may also be an entire folder of files. the entire folder will be published as-is with hierarchy intact.
      - [`<template_files>` (link) ](/keys/templates) - template files are processed for [template variables](/templates). templates contain the content of your stack displayed in edit mode, as well as the files that are published with your stack. the only difference between a template and an asset is that templates are processed for template variables.
      - [`<library_files>` (link) ](/keys/libraries) - your stack can include built-in stack libraries (like jQuery) or libraries that your stacks include. included libraries are similar to assets, but are shared by more than one stack. if two stacks include the same library only one copy will be published with the stack.

### The Property List — Info.plist
All of the properties that will be used for your stack are stored in the Info.plist file. You can learn more about it in the Info.plist document. A stack without an Info.plist file will not be loaded by stack.


### Resources
All of the files (other than the Info.plist) used by your stack should be stored inside the `Resources` folder. This includes all of the templates, assets, and anything else your stack requires.


### More Stacks
You can place a complete stack bundle inside the Resources folder of another stack. This allows a number of related stacks to be installed from a single Finder icon. If many stacks are delivered this way in a bundle, only the top-most stack should include an automatic updater URL. In this way all of the stacks will be updated as a single bundle.