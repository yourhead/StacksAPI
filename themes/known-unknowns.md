---
title: Theme API — Known Unknowns
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

The available schema is explicitly inferred and open-ended. The following areas need additional runtime tests or confirmation from the Stacks developers.

## Inheritance

- The independent effect of theme-level `inheritsFrom`.
- Whether controls, frontmatter or other properties merge across the `parent` chain.
- Behaviour when a parent is missing or circular inheritance is declared.
- Whether parent resolution has version constraints.

## Template language

- The complete function list beyond demonstrated functions such as `@count`.
- All supported operators and coercion rules.
- Truthiness and missing-property behaviour.
- Exact scope and lifetime of loop variables.
- Escaping filters for HTML, attributes, URLs, CSS and JavaScript.
- Error reporting for malformed YAML and expressions.
- Whether duplicate template IDs in one bundle have deterministic precedence.

## Runtime objects

- Complete schemas for `site`, `page`, navigation pages, breadcrumbs and theme objects.
- Which properties are stable public API and which are debugging implementation details.
- The Theme API version property's exact name and format.
- Availability differences between Edit, Preview and Publish.

## Assets and libraries

- Complete library descriptor fields accepted specifically by themes.
- Which libraries are included in Edit mode.
- Deduplication and version-conflict behaviour.
- Asset collision behaviour across themes, layouts and stacks.

## Layouts

- Exact precedence when both a layout and theme provide page-level structure.
- The complete list of layout content insertion points.
- Whether layout templates participate in the same named-template inheritance chain.

## Development lifecycle

- Which `.devstackstheme` changes hot-reload reliably.
- Which metadata changes require reselecting the theme or reopening the project.
- Compatibility guarantees across Theme API runtime versions.

## How to document new findings

For each test, record:

1. Stacks version and build.
2. macOS version.
3. Minimal theme bundles used by the test.
4. Edit, Preview and Publish results.
5. Generated HTML/CSS/JavaScript where relevant.

Once behaviour is repeatable, move it from this page into the appropriate reference page and label it **Observed** until it becomes formally specified.
