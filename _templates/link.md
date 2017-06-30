---
name: Link Property Value
syntax: "%id=linkProperty%"
group: properties and controls
description: The output of link controls.
available: 10


---




> NB: The link template was available in API v1.  Property extraction was added API v3.  Property writing was added in API v10.


### Usage

#### Basic Syntax

```html
%id=<linkID>%
```

 - `<linkID>` — The property ID of the link control. The output of this form is the first half of an anchor tag. **You must close the tag yourself.**


<hr>

#### Attribute Extraction Syntax

 ```html
 %id=<linkID> -<attributeName>%
 ```

  - `<linkID>` — The property ID of the link control. The output of this form is the first half of an anchor tag. **You must close the tag yourself.**
  - `<attributeName>` — The attribute name to return (e.g. `href`).

 Extract a specific attribute such as the href or rel attribute. The template is replaced by just the specified attribute value. The rest of the link is discarded. This is useful for extracting the href value from a link to build your own specialized link.

 > Only a single attribute can be extracted. If multiple attributes are specified the behavior is undefined.
<hr>

#### Property Append Syntax

 ```html
 %id=<linkID> +<propertyName>="<stringValues>"%
 ```

  - `<linkID>` — The property ID of the link control. The output of this form is the first half of an anchor tag. **You must close the tag yourself.**
  - `<attributeName>` — The attribute name to append the value to.
  - `<stringValues>` — A space-separated list of string values.

 Append items to an attribute. Useful for appending CSS classes to your links.

 Attribute strings are formatted like classes (i.e. as a list of space-separated identifiers). Your new identifiers are added to the current list. Duplicate items are discarded. The resulting order of the identifiers is undefined.

 The stringValues should not be an empty string. The strings are NOT encoded but treated as literals. If the values are pulled from a `%html%` then property text encoding should be applied.

 > Only a single attribute can be modified. If multiple attributes are specified the behavior is undefined.

<hr>

#### Property Override Syntax

 ```html
 %id=<linkID> -<propertyName>="<any string>"%
 ```

  - `<linkID>` — The property ID of the link control. The output of this form is the first half of an anchor tag. **You must close the tag yourself.**
  - `<propertyName>` — The property name to return (e.g. `href`).
  - `<stringValue>` — Any string value.

 Override a property in a link. Any existing value in the link will be replaced by your value. The new string must have some value.

 The stringValues should not be an empty string. The strings are NOT encoded but treated as literals. If the values are pulled from a `%html%` then property text encoding should be applied.

 > Only a single attribute can be overridden. If multiple attributes are specified the behavior is undefined.



### Description

If the Property Extraction syntax is used then the template will be replaced by the value of that property.

Otherwise the template of this form is the *first half* of an anchor tag. **You must close the tag yourself.**





#### Example 1: a simple link in HTML.

```html
%id=linkContorlID%Click Here</a>

<!--
Input:  <a href="https://google.com" title="Untitled" class="enabled">
Result: <a href="https://google.com" title="Untitled" class="enabled">Click Here</a>
-->
```


#### Example 2: extract the href to use as a CSS URL.

```css
.backgroundImageClass {
    background-image: url("%id=linkControlID -href%");
}

/*
Input:  <a href="https://google.com" title="Untitled" class="enabled">
Result: background-image: url("https://google.com");
*/
```


#### Example 2: replace the target attribute with `_blank`

```html
%id=linkContorlID -target="_blank"%Click Here</a>

<!--
Input:  <a href="https://google.com" title="Untitled" class="enabled">
Result: <a href="https://google.com" title="Untitled" class="enabled target="_blank">Click Here</a>
-->
```



#### Example 2: add the `enabled` and `button` to the class attribute

```html
%id=linkContorlID +class="enabled button"%Click Here</a>

<!--
Input:  <a href="https://google.com" title="Untitled" class="enabled">
Result: <a href="https://google.com" title="Untitled" class="button enabled">
-->
```
