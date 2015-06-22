---
name: Conditional
syntax: "%[if true ]% %[else]% %[endif]%"
group: expressions and conditionals
description: Conditional content based a property value.
available: 3

---



### Usage

```html
%[if <expression>]%
    content displayed when <expression> is true
%[endif]%
```
or 

```html
%[if <expression>]%
        content displayed when <expression> is true
%[else]%
    content displayed when <expression> is false
%[endif]%
```

 - `<expression>` can be integer or boolean property (e.g. `%id=checkBoxValue%`) or an expression that evaluates to an integer or boolean (e.g. `%( %id=count% < 1 )%`). 

 > Note: Integer values are converted to boolean using the C language rules (e.g. 0 => False, all other values => True).

### Description

Conditionals allow you to add or remove content to the generated HTML based on the value of the conditional argument. 

Conditionals may be nested.

#### Example 1: Display a message when checkbox is checked.

```html
%[if %id=checkbox% ]%
    Checkbox is checked.
%[endif]%
```

#### Example 2: Display an element using CSS when a checkbox is checked.

```css
.elementClass {
    %[if %id=checkbox% ]%
        display: block;
    %[else]%
        display: none;
    %[endif]%
}
```

