---
title: Stack API
layout: page
api_section: stack
back:
  - top: /
links:
  - top: /bundle
  - top: /plist
  - plist: plist/controls
  - top: /templates
---

The Stack API is for building reusable elements that people add to a Stacks page. A stack can provide content, controls, layout, behavior and supporting resources.

### Start here

- [Stack bundles]({{ site.baseurl }}/bundle/) explains the bundle structure and where files belong.
- [Property List Reference]({{ site.baseurl }}/plist/) documents stack metadata and configuration.
- [Custom Controls Reference]({{ site.baseurl }}/plist/controls/) covers controls shown in the inspector.
- [Template Variables Reference]({{ site.baseurl }}/templates/) documents values available to stack templates.

### What is a stack?

A stack is one element in a Stacks layout. Every item added from the library is a stack. Stacks supplies an outside container, while the bundle supplies the inner content and defines its HTML, CSS, JavaScript, PHP, configurable properties and supporting resources.

In this documentation, **Stacks** refers to the application or platform, while **stack** refers to an individual page-building element created with the Stack API.

### Where are stacks installed?

The built-in stacks reside inside the Stacks application bundle and should not be modified. Third-party stacks are installed in the Stacks application-support folder.

For development, use the `.devstack` extension. Stacks monitors development bundles for changes and provides additional logging. Finished products should use the `.stack` extension.

### What is inside a stack?

A stack uses a standard macOS bundle structure. Its `Contents` folder contains an `Info.plist` and a `Resources` folder holding templates, libraries, assets and other files required by the stack.

[Continue with stack bundles →]({{ site.baseurl }}/bundle/)
