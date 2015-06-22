---
name: Link Property Value
syntax: "%id=linkProperty%"
group: properties and controls
description: The output of link controls.
available: 3


---



### Usage

##### Anchor Tag Syntax

```html
%id=<linkID>%
```

 - `<linkID>` — The property ID of the link control. The output of this form is the first half of an anchor tag. **You must close the tag yourself.**





##### Property Syntax

```html
%id=<linkID> -<propertyName>%
```

 - `<linkID>` — The property ID of the link control. The output of this form is the first half of an anchor tag. **You must close the tag yourself.**
 - `<propertyName>` — The property name to return (e.g. `href`).

The alternate usage of a link is to extract a specific property such as the href or rel property and replace the template with only that.






### Description

The output of this form is the first half of an anchor tag. **You must close the tag yourself.**

The alternate usage of a link is to extract a specific property such as the `href` or `rel` property.





#### Example 1: a simple link in HTML.

```html
%id=linkContorlID%Click Here</a>
```

#### Example 2: extract the href to use as a CSS URL.

```css
.backgroundImageClass {
    background-image: url("%id=linkControlID -href%");
}
```
