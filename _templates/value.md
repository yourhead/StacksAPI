---
name: Property Value
syntax: "%id=propertyID%"
group: properties and controls
description: Property values from controls.
available: 2

---



### Usage

```html
%id=<property_id>%
```

 - `<property_id>` - The name of the property to return.

{% include newstuff.html %}
or for control arrays

```html
%id=<property_id>[<index>]%
```

 - `<property_id>` - The name of the property to return.
 - `<index>` - The index of the array item. Indexes count from zero.


### Description

This template returns the value of a property. Properties and their corresponding controls are defined in the Info.plist file. When a user changes the properties by adjusting the controls, this value will change in real time.



#### Example 1: use the value of an slider.

template:

```html
The slider value is: %id=slider_id%
```

exported HTML with the slider set to 10:

```html
The slider value is: 10
```



{% include newstuff.html %}
#### Example 2: use two number fields in a control array.

template:

```html
Image size to: %id=number_id[0]% x %id=number_id[1]%
```

exported HTML with the values 800 and 600 in the number fields:

```html
Image size to: 800 x 600
```





{% include newstuff.html %}
#### Example 3: use radio buttons to change text alignment

template:

```css
.myTextClass {
    text-alignment:
        %[if %id=radioButton[0]% ]%  left;    %[endif]%
        %[if %id=radioButton[1]% ]%  center;  %[endif]%
        %[if %id=radioButton[2]% ]%  right;   %[endif]%
}
```

exported CSS with the middle button pushed:

```css
.myTextClass {
    text-alignment:
          center;
}
```







