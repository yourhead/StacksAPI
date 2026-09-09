---
title: Theme Templates
layout: page
api_section: theme
back:
  - top: /themes
links:
  - title: Runtime Properties
    url: /themes/runtime
  - title: Inheritance
    url: /themes/inheritance
  - title: Reference Themes
    url: /themes/reference-themes
---

Theme templates use `:( ... ):` expressions and YAML frontmatter. This is distinct from the `%...%` template replacement syntax used by normal stack templates.

## Frontmatter

A template begins with YAML between `---` markers:

```yaml
---
id: navitem
title: Navigation Item
description: Renders one page in the navigation tree.
---
```

### id

`id` names the template. Includes and parent-theme overrides resolve templates using this value.

The default top-level page unit has the ID `page`.

### Other properties

Frontmatter may contain strings, numbers, booleans, objects and arrays:

```yaml
---
id: footer
copyright: 2026
footerLinks:
  - title: Privacy
    link: /privacy.html
  - title: Contact
    link: /contact.html
---
```

Properties defined in a template are available to that template. The Sample theme demonstrates that they are also available to templates included by it.

## Property output

```text
:(site.title):
:(page.title):
:(copyright):
```

Whitespace inside an expression is optional in the bundled examples.

## Includes

```text
:(include "head"):
:(include nav):
:( include "foot" ):
```

The bundled themes demonstrate quoted and unquoted template IDs. Quoted IDs are clearer and are recommended for authored documentation and examples.

## Conditions

```text
:( if site.copyright.length ):
    :( site.copyright ):
:( else ):
    :( copyright ):
:( end ):
```

## Loops

```text
:( for navpage in site.pages.children ):
    :( include "navitem" ):
:( end ):
```

The loop variable is visible to templates included from inside the loop. The Sample theme uses this to let `navitem` read `navpage`.

`__index` is demonstrated as the zero-based or sequence index for the current loop iteration; the exact indexing contract should be tested before depending on its first value.

## Functions and operators

The Sample theme demonstrates:

```text
:(if @count(navpage.children) < 1 ):
```

This confirms the `@count` function and ordinary comparison operators in an expression. The complete function and operator set is not described by the schema.

## Standard templates

The bundled Base theme establishes these conventional units:

- `page` — doctype and top-level `<html>` structure.
- `head` — metadata, title and generated stylesheet content.
- `body` — navigation, page body and footer placement.
- `foot` — bottom-of-body content and JavaScript.
- `css` — theme CSS exported as `stacks.css`.
- `js` — theme JavaScript exported as `stacks.js`.

It also includes runtime-provided templates such as `head_meta`, `head_css`, `theme_foot` and `foot_js`. These are demonstrated by Base but are not fully enumerated in the schema.

## Generated CSS and JavaScript

The Blank theme demonstrates explicit path properties:

```html
<link rel="stylesheet" href=":(siteCssPath):">
<link rel="stylesheet" href=":(layoutCssPath):">
<link rel="stylesheet" href=":(pageCssPath):">
<script src=":(pageJsPath):"></script>
```

When inheriting Base, prefer its `head` and `foot` templates unless the theme needs a fully custom document structure. That keeps generated resource placement aligned with Stacks.
