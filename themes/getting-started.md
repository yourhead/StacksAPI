---
title: Theme API — Getting Started
layout: page
back:
  - top: /themes
links:
  - title: Theme Bundles
    url: /themes/bundle
  - title: Templates
    url: /themes/templates
  - title: Inheritance
    url: /themes/inheritance
---

This example creates a small theme that inherits the standard page structure from the bundled Base theme and overrides only the body and CSS templates.

## 1. Create the bundle

During development, use the `.devstackstheme` extension so Stacks can notice changes without treating the folder as a finished distributable bundle.

```text
My Theme.devstackstheme/
└── Contents/
    ├── Info.plist
    └── Resources/
        └── Templates/
            ├── body.html
            └── css.css
```

**Observed:** `.devstackstheme` is useful during development. Distribute the finished bundle as `.stackstheme`.

## 2. Add Info.plist

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
  "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>CFBundleIdentifier</key>
    <string>com.example.stacks.theme.mytheme</string>

    <key>CFBundleShortVersionString</key>
    <string>1.0.0</string>

    <key>CFBundleVersion</key>
    <string>1000</string>

    <key>title</key>
    <string>My Theme</string>

    <key>subtitle</key>
    <string>A minimal derived theme.</string>

    <key>type</key>
    <string>theme</string>

    <key>parent</key>
    <string>com.yourhead.stacks.theme.base</string>

    <key>preprocessor</key>
    <true/>
</dict>
</plist>
```

`CFBundleIdentifier`, `title` and `type` are required by the bundled schema. The value of `type` must be `theme`.

## 3. Override the body template

`Contents/Resources/Templates/body.html`:

```html
---
id: body
description: The body supplied by My Theme.
---

<body>
    :( content.bodyAbove ):

    <main class="site-content">
        :( content.body ):
    </main>

    :( include "foot" ):
</body>
```

The filename is not what performs the override. The YAML frontmatter value `id: body` matches the Base theme's body template ID.

The body preserves three important behaviours:

- `content.bodyAbove` inserts page-scoped content above normal stacks.
- `content.body` inserts the page's editable Stacks content.
- The inherited `foot` template inserts bottom-of-body content and JavaScript.

## 4. Add theme CSS

`Contents/Resources/Templates/css.css`:

```css
---
id: css
---

:root {
    --content-width: 70rem;
}

body {
    margin: 0;
    font-family: system-ui, sans-serif;
}

.site-content {
    width: min(100% - 2rem, var(--content-width));
    margin-inline: auto;
}
```

The standard `css` template is exported as `stacks.css` in the theme output.

## 5. Install and test

Place the development bundle in the Stacks Themes folder, select it for a site and check all three modes:

- Edit mode
- Preview
- Published output

Also verify pages at different nesting levels. Paths that work on the home page can still fail on child pages if they were written as fixed relative URLs.

## A fully independent theme

A theme does not have to use Base. It may supply its own `page`, `head`, `body`, `css` and `js` templates. If doing so, compare it carefully with [Blank Theme](/themes/reference-themes) and preserve every required `content.*` insertion point and generated CSS/JavaScript path.
