---
name: Image Container
syntax: "%image%"
description: The content of an Image stack.
available: 1

---



### Usage

```html
%image%
```

or with default transforms:


```html
%image imageScaleMode=1 imageMaxWidth=100 imageMaxHeight=100%
```

 - default properties - Default values for the image editing properties can be included. Any of the properties defined for the Image Transform control may be used. 

 > Note: default properties are not immutable. The user can change these by editing the image. For immutable image modifications use an Image Transform. 
(Available: Stacks API 3+)


### Description

A image container and the content of an Image stack.

