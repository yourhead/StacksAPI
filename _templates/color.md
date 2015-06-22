---
name: Color Values
syntax: "%id=colorID%"
group: properties and controls
description: Output of a color control.
available: 3


---



### Usage

```html
%id=<colorControlID>% 
%id=<colorControlID> <operation> n%
```

 - `<colorControlID>` is the ID of a color control.
 - `<operation>` is a color math operation, one of: `+`, `-`, or `*`.
   - `+` and `*`  lighten the color
   - `-` darkens the color ( * 0.5 darkens )



### Description

Color values output as HTML hex color strings.

Color Math operations can be used to modify the colors.



#### Example 1: Color math used in CSS

```css
    /* lighten the color by 25/255ths */
    .lighterStuff {
      background-color: %id=userSelectedColor + 25%;
    }

    /* darken the color by 25/255ths */
    .darkerStuff {
      background-color: %id=userSelectedColor - 25%;
    }

    /* twice as light */
    .lightestStuff {
      background-color: %id=userSelectedColor * 2%;
    }

    /* twice as dark */
    .darkestStuff {
      background-color: %id=userSelectedColor * 0.5%;
    }

```






