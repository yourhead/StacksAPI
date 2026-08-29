---
title: Theme Info.plist
layout: page
back:
  - top: /themes
links:
  - title: Theme Bundles
    url: /themes/bundle
  - title: Inheritance
    url: /themes/inheritance
  - title: Existing Control Reference
    url: /plist/controls
---

## Required properties

The bundled schema requires three root properties.

### CFBundleIdentifier

- Type: String
- Purpose: Unique theme identifier used by the loader and parent-theme references.

Use a stable reverse-domain identifier. Changing it creates a different theme and can break existing projects that reference the previous identifier.

### title

- Type: String
- Purpose: User-facing theme name.

### type

- Type: String
- Required value: `theme`

```xml
<key>type</key>
<string>theme</string>
```

## Optional properties

The schema recognises these optional root properties:

- `subtitle` — String
- `parent` — String
- `inheritsFrom` — String
- `icon` — String
- `author` — String
- `CFBundleShortVersionString` — String
- `CFBundleVersion` — String
- `preprocessor` — Boolean
- `tags` — Array of strings
- `assets` — Array of asset descriptors
- `libraries` — Array of library descriptors
- `customItems` — Array of control dictionaries

The schema describes the plist as open-ended at runtime. Unknown properties should therefore be preserved by authoring tools even when they cannot be edited.

## Version values

The bundled themes use a user-facing dotted version and a monotonically increasing build string:

```xml
<key>CFBundleShortVersionString</key>
<string>1.2.0</string>

<key>CFBundleVersion</key>
<string>1200</string>
```

## Parent themes

`parent` contains the `CFBundleIdentifier` of the theme whose templates should be loaded first.

```xml
<key>parent</key>
<string>com.yourhead.stacks.theme.base</string>
```

See [Theme Inheritance]({% include docs-root.html %}/themes/inheritance) for the distinction between confirmed `parent` behaviour and the less completely documented `inheritsFrom` key.

## Controls

`customItems` exposes controls in the theme inspector. The Sample theme states that all normal Stacks API controls are available to themes.

```xml
<key>customItems</key>
<array>
    <dict>
        <key>id</key>
        <string>contentWidth</string>
        <key>title</key>
        <string>Content Width</string>
        <key>type</key>
        <string>select</string>
        <key>default</key>
        <integer>1100</integer>
        <key>items</key>
        <array>
            <dict>
                <key>title</key><string>Compact</string>
                <key>value</key><integer>960</integer>
            </dict>
            <dict>
                <key>title</key><string>Wide</string>
                <key>value</key><integer>1280</integer>
            </dict>
        </array>
    </dict>
</array>
```

The selected value is available to theme templates by property name:

```css
.site-content {
    max-width: :(contentWidth):px;
}
```

Theme controls use the existing [Custom Controls Reference]({% include docs-root.html %}/plist/controls).

## Assets and libraries

Assets use dictionaries with a required `filename` and optional `siteAsset` value:

```xml
<key>assets</key>
<array>
    <dict>
        <key>filename</key>
        <string>assets</string>
    </dict>
</array>
```

Libraries are an array of dictionaries. The schema requires each library to have a `name` and permits additional library properties:

```xml
<key>libraries</key>
<array>
    <dict>
        <key>name</key>
        <string>jQuery3</string>
    </dict>
</array>
```

Library names are resolved by Stacks. A name is not itself a URL or filename.

## Preservation rule for authoring tools

Because the schema is inferred and explicitly permits runtime expansion, an editor should round-trip unknown plist keys and unknown dictionary members unchanged. Loading and saving a theme must not silently reduce it to only the properties currently understood by the editor.
