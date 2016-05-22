---
name: Button
type: button
array: button-2, button-3, button-4
description: Like a checkbox, but graphical.
value: any value
available: 7
generics: true

properties:
  - title: Icons
    key: icons
    type: Array of Numbers
    default: no icon
    description: An array of Unicode values (integers) of Font Awesome icons. If using a button array, provide one value for each button. See description above for Font Awesome details.

  - title: Radio Buttons
    key: radio
    type: boolean
    default: False
    description: Radio buttons will allow only one button in the group to be pushed.

  - title: True Value
    key: trueValue
    type: string
    default: True
    description: When the button is pressed this value will be used in replacement templates. In arrays, this may be an arrof of strings.

  - title: False Value
    key: falseValue
    type: string
    default: False
    description: When the button is unpressed this value will be used in replacement templates. In arrays, this may be an arrof of strings.

  - title: Default Value
    key: default
    type: string
    default: False (not pushed in).
    markdown: yes

---


A Button has all the properties of a checkbox. It represents a boolean value that is either true (pushed in) or false (default). Like checkboxes the output value of a button can be set to any specific value by using the True Value and False Value properties.


### Radio Mode

Checkboxes arrays can be used where only one of the group is allowed to be checked at a time.  To use checkboxes in this mode use one of the array types (see below) and enable the Radio property.


### Button Array

Button controls can be used in arrays.  Each has its own icon, subtitle, trueValue, falseValue, and default, all other values are shared.  Button types are:

> NB: trueValue/falseValue arrays requires Stacks API v8 (Stacks v3.1+).

- `button` : a regular button.
- `button-2` : two buttons.
- `button-3` : three buttons.
- `button-4` : four buttons.


### Button Icons
A checkbox can also display an Icon.  All the icons from the Stacks UI, including your custom buttons, come from the Font Awesome library package.  This gives Stacks a single unified cohesive UI even while allowing a significant amount of customization.

You can choose from over 500 custom icons on the [Font Awesome Icons](http://fortawesome.github.io/Font-Awesome/icons/) page. Set the icons property of your button to the Unicode value of the icon you would like to display.  Stacks will take care of rendering the icon for all the needed button states for Mac OS X. 

**The icons labeled "cube" and "cubes" are reserved for Stacks internal use.**

> Hint: To find the Unicode value of a Font Awesome icon click through to the icon's page (e.g. [Birthday Cake icon](http://fortawesome.github.io/Font-Awesome/icon/birthday-cake/)). The Unicode value is listed below the icon previews.  (e.g. Unicode f1fd for Birthday Cake).  You can enter this value directly into a PList editor as a hex value, just enter 0x before the listed value (e.g. type "0xf1fd" in the Xcode PList editor). You can also convert that hex value to a regular integer using Calculator.app (e.g. f1fd = 61949).




