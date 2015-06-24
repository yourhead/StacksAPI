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


Color Math operations can be used to modify the colors.

{% include newstuff.html %}
#### Color with opacity 

Color values output as rgba CSS color strings including opacity if it is enabled.


#### Example 1: Color math used in CSS

template:

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

With <span style='font-weight:900; color: rgba(255, 0, 128, 1.0);'>THIS COLOR (rgba(255, 0, 128, 1.0))</span> chosen.

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

which should render like this:

<style>
    .lighterStuff {
      background-color: rgba(255,26,153,1.0);
    }

    /* darken the color by 25/255ths */
    .darkerStuff {
      background-color: rgba(230,0,103,1.0);
    }

    /* twice as light */
    .lightestStuff {
      background-color: rgba(255,0,255,1.0);
    }

    /* twice as dark */
    .darkestStuff {
      background-color: rgba(128,0,64,1.0);
    }

    .originalStuff {
      background-color: rgba(255,0,128,1.0);
    }

    .lighterStuff, .darkerStuff, .lightestStuff, .darkestStuff , .originalStuff {
      color: white;
      font-weight: 900;
      padding: 2px 10px;
      border-radius: 4px;
      text-align:center;
    }

</style>

<p class='originalStuff'>Original</p>
<p class='lighterStuff'>Lighter Stuff</p>
<p class='darkerStuff'>Darker Stuff</p>
<p class='lightestStuff'>Lightest Stuff</p>
<p class='darkestStuff'>Darkest Stuff</p>





