---
name: Icon File
key: icon
type: String
description: The base of you icon files.
required: yes
available: 7
---

The base name of your stack's icon files.

***New in Stacks API v7***

The library displays 3 icon sizes and can be viewed in both Hi-DPI (Retina) and standard displays.  This means that there are potentially 6 icon sizes to create.

In your plist you provide the base name of the icon file. Stacks will look for the various sizes using this name.  You should name your files following this convention:

### Retina
   - Large Icon (128x128): `<base_name>_large@2x.png`
   - Medium Icon (64x64): `<base_name>_medium@2x.png`
   - Small Icon (32x32): `<base_name>_small@2x.png`

### Standard DPI
 - Large Icon (64x64): `<base_name>_large.png`
 - Medium Icon (32x32): `<base_name>_medium.png`
 - Small Icon (16x16): `<base_name>_small.png`


**It is recommended to create an icon for each size. However if you provide only some sizes, Stacks will scale the avialable icons to fit the sizes that are not available.**


> Note: All older icon file standards are supported in Stacks 3, icon images are scaled to fit the new sizes which reduces the quality of the icon image.  It is recommended to add all the new icon sizes.  There are several open source icon templates and help apps available on [the YourHead GitHub](http://github.com/yourhead/).
