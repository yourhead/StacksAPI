---
title: Theme API
layout: page
api_section: theme
back:
  - top: /
links:
  - title: Getting Started
    url: /themes/getting-started
    description: Create and install a minimal theme.
  - title: Theme Bundles
    url: /themes/bundle
    description: Bundle structure, resources and development bundles.
  - title: Info.plist Reference
    url: /themes/plist
    description: Theme metadata, controls, assets and libraries.
  - title: Templates
    url: /themes/templates
    description: Template IDs, frontmatter and page composition.
  - title: Runtime Properties
    url: /themes/runtime
    description: Site, page, navigation and content values.
  - title: Inheritance
    url: /themes/inheritance
    description: Parent themes and template overrides.
  - title: Reference Themes
    url: /themes/reference-themes
    description: What Base, Blank and Sample demonstrate.
  - title: Known Unknowns
    url: /themes/known-unknowns
    description: Behaviour that is not yet fully specified.
---

The Theme API lets a bundle provide the complete HTML document around a Stacks page. A theme can define the document structure, metadata, navigation, page content area, footer, stylesheets, scripts and controls shown in the theme inspector.

Themes use a new template language based on named templates, YAML frontmatter and runtime objects such as `site`, `page` and `content`. This is separate from the `%...%` replacement syntax used by ordinary stack templates.

## Documentation status

The Theme API does not yet have a published, authoritative reference. This section is based on:

1. The `theme.schema.json` file bundled with Stacks.
2. The bundled Base, Blank and Sample themes.
3. Behaviour observed while developing themes in Stacks.

The bundled schema calls itself an **inferred schema**. It is useful evidence, but it also says that the runtime may support more values than the schema currently lists.

Pages in this section use the following labels:

- **Schema** — explicitly described by the bundled schema.
- **Bundled theme** — demonstrated by Base, Blank or Sample.
- **Observed** — verified during development, but not formally specified.
- **Unconfirmed** — accepted or suggested by available files, but its complete behaviour is unknown.

## What a theme controls

A theme can provide:

- The top-level HTML document and language attribute.
- The contents of `<head>` and `<body>`.
- Placement of Stacks-generated CSS and JavaScript.
- Navigation generated from the site page hierarchy.
- Theme-wide controls through `customItems`.
- Static assets and shared libraries.
- Reusable partial templates.
- A parent theme whose templates can be selectively overridden.

Start with [Getting Started]({% include docs-root.html %}/themes/getting-started), then use the remaining pages as a practical reference.
