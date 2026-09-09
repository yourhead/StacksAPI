---
title: Bundled Reference Themes
layout: page
api_section: theme
back:
  - top: /themes
links:
  - title: Getting Started
    url: /themes/getting-started
  - title: Templates
    url: /themes/templates
  - title: Inheritance
    url: /themes/inheritance
---

Stacks includes three reference themes inside the application bundle:

```text
Stacks.app/Contents/Resources/Themes/
├── base.stackstheme
├── blank.stackstheme
└── sample.stackstheme
```

The same directory contains `theme-spec/theme.schema.json`.

## Base Theme

Bundle identifier:

```text
com.yourhead.stacks.theme.base
```

Base provides the standard HTML5 composition:

- `page` surrounds the document with prefix, doctype, `<html>` and suffix.
- `head` inserts head-above content, metadata, title, CSS and head-below content.
- `body` inserts body-above content, navigation, the main page body and foot.
- `foot` inserts theme foot content, body-below content and JavaScript.
- `css` and `js` provide conventional generated output units.

Base is intended to be inherited and selectively overridden.

## Blank Theme

Bundle identifier:

```text
com.yourhead.stacks.theme.blank
```

Blank has Base as its `parent`, but overrides the main document units with minimal implementations. It is particularly useful for identifying the content and resource paths that a custom document must preserve:

- `content.prefix` and `content.suffix`
- `content.headAbove` and `content.headBelow`
- `content.bodyAbove`, `content.body` and `content.bodyBelow`
- `siteCssPath`, `layoutCssPath`, `pageCssPath` and `pageJsPath`

Use Blank as a reference when creating an intentionally unstyled canvas.

## Sample Theme

Bundle identifier:

```text
com.yourhead.stacks.theme.sample
```

Sample demonstrates:

- Standard controls in `customItems`.
- Asset and library declarations.
- Parent-theme inheritance.
- Theme template overrides.
- YAML frontmatter objects and arrays.
- Includes and property propagation.
- Conditions and loops.
- Navigation with nested child pages.
- Breadcrumbs.
- Site, page and parent-theme runtime properties.
- A Bootstrap-oriented page composition.

Sample is the broadest executable example, but it is still an example rather than a complete formal specification.

## Source precedence

When evidence differs, use this order cautiously:

1. Behaviour observed in the current Stacks runtime.
2. Current bundled reference themes.
3. Current bundled inferred schema.
4. Assumptions borrowed from the ordinary Stack API.

Record discrepancies instead of silently choosing whichever interpretation is most convenient.
