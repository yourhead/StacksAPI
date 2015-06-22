---
name: Icon File
key: icon
type: string
description: The base of you icon files.
required: yes
available: 5

links:
  - top: /plist

---
The base name of your stack's icon files. 

The library displays a smaller 50x50 pixel icon image in the grid view. When a users selects your icon, it will display a 58x58 pixel image in the library detail view. You must provide an icon file for each of these images.

Each icon file should be PNG format and have the .png extension. A unique app-shaped icon with a transparent background is recommended. The file names for the icons should be in the format:


```
<base_name>@<size>.png
```


 * `<base_name>` is the name that you provide in the property. 
 * `<size>` is the width of the image. Current supported sizes are: 50 and 58.

Example
In the plist file: 

```xml
<key>icon</key>
<string>MyGreatIcon</string>
```

Files in the resources folder: 

```
MyGreatIcon@50.png 
MyGreatIcon@58.png 
```
