---
title: Theme Inheritance
layout: page
back:
  - top: /themes
links:
  - title: Getting Started
    url: /themes/getting-started
  - title: Templates
    url: /themes/templates
  - title: Reference Themes
    url: /themes/reference-themes
---

## parent

**Schema:** Parent-theme templates are loaded first. A child theme overrides a parent template by supplying another template with the same frontmatter `id`.

```xml
<key>parent</key>
<string>com.yourhead.stacks.theme.base</string>
```

Base's plist comments describe the same model:

1. Set `parent` to `com.yourhead.stacks.theme.base`.
2. The child inherits templates from Base.
3. Supply a template with the same ID to override one unit.

For example, a child can provide `id: body` while continuing to use Base's `page`, `head`, `foot`, `css` and `js` templates.

## Override identity

The template ID performs the override:

```yaml
---
id: body
---
```

Do not assume that copying the parent's filename is sufficient if the frontmatter ID is missing or different.

## inheritsFrom

The schema accepts `inheritsFrom` as an optional string. Sample includes both:

```xml
<key>parent</key>
<string>com.yourhead.stacks.theme.base</string>

<key>inheritsFrom</key>
<string>com.yourhead.stacks.theme.base</string>
```

Blank uses `parent` without `inheritsFrom` and still demonstrates parent-template inheritance.

**Unconfirmed:** The independent effect of theme-level `inheritsFrom` is not explained by the theme schema or comments. In the normal Stack API, `inheritsFrom` imports controls and properties from another stack. It may perform an analogous property role for themes, but this should not be treated as confirmed theme behaviour without a focused test.

Authoring tools must preserve both keys independently. They must not rewrite one as the other or silently add/remove either key.

## Missing parents

The available files do not specify loader behaviour when the parent identifier cannot be resolved. A distributed child theme should therefore avoid depending on a third-party parent unless that dependency is installed with it and versioned carefully.

## Recommended approach

Use Base as the parent when the theme only needs to replace selected presentation units. Build a fully independent document only when the theme deliberately needs control over the complete HTML structure and has tests for all standard insertion points.
