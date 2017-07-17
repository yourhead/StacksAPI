---
title: The Stacks API
layout: page
links:
  - top: /bundle
  - top: /plist
  - plist: plist/controls
  - top: /templates
---


### Overview

The Stacks library comes with a set of built-in, general purpose stacks that are great for creating a page layout, but if you're familiar with Mac OS X, HTML and CSS you can create your own stacks to add to the Stacks library.

This document describes how to build your own stacks and gives a reference to the available options in the API.

There's an active community of stack developers that discuss how to build, market, and sell stacks on our Slack channel.  If you need help, have questions, or just want to hear what other developers are doing, this is the place. The channel is open to the public but you need to sign up at:

 * Sign Up:  [http://slack.yourhead.com](http://slack.yourhead.com)
 * Log In:  [http://yourhead.slack.com](http://yourhead.slack.com)


### What is a stack
A stack is one element in a Stacks layout. Any item that can be added to a Stacks layout comes from the library. Each item in the library is a stack. An outside container (usually two divs) that Stacks provides and the inner content of the stack, which comes from stack's bundle. The bundle of each stack has a number of files which specify the custom properties, the HTML/CSS/JS/PHP content, and any other file assets the stack needs.

> Note: In this document we will use the term **Stacks** (capitalized and plural) to refer to the plugin. We will use the term **stack** (lowercase and singular) to refer to the layout elements that you create with the Stacks API.


### Where do stacks get installed
Each default stack resides inside of the Stacks plugin bundle. You can view them (but you should not modify them) by right-clicking on the Stacks.rwplugin file and choosing **Show Package Contents**. To install your own stacks into you should add them to the Stacks folder.

The Stacks folder can be found in: `~/Library/Containers/com.realmacsoftware.rapidweaver/Data/Library/Application Support/RapidWeaver`

If this folder doesn't yet exist, it will be created the first time you use Stacks.


### Working with bundles
On Mac OS X, a bundle is a folder with a file extension that belongs to an application. These folders appear as a single file to the user. Double clicking them launches the owning app rather than opening the folder. RapidWeaver has graciously done this for folders with the .stack extension. So if you have RapidWeaver installed any stack you create should immediately gain the stack icon and open RapidWeaver when double-clicked.

> Note: RapidWeaver will install a double-clicked stack into the Stacks folder.

#### Dev stack folders
While working on a stack you can change the extension to .devstack. Stacks will recognize a folder with the `.devstack` extension, but it will not be bundled in the Finder.  This makes it a bit easier to work with.

Dev stacks also behave a bit differently inside Stacks. Stacks will monitor the files inside of a dev stack and refresh edit mode when there changes to the files.

This extra monitoring and extra logging takes a lot of extra work. For this reason Stacks limits the number of devstacks to 20.

Dev stacks also cause Stacks to do more logging in the developer console. When a dev stack is being updated Stacks will log more detailed information about the automatic check/update/install process.

> Warning: Do not ship a dev stack to a customer. Dev stacks cause Stacks to do a bit of extra work in logging and file monitoring. For the best experience customers should always use the .stack extension.


### What's inside a stack
A stack is built as a standard Mac OS X bundle. This means that it's a folder with a very specific structure. Inside the folder you'll find a Contents folder and inside of that you'll find the property list and the stack's resources. You can use this reference to build your own from scratch, but it's probably easier to start from a copy of one of the built-in stacks.
.










