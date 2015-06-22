---
name: Conditional Display
syntax: "%[if edit]%  %[endif]%"
group: expressions and conditionals
description: Enable content only for Edit, Preview, or Publish.
available: 2

---



### Usage

```html
%[if edit]%  
    any content
%[endif]%  
```

or

```html
%[if !edit]%  
    any content
%[endif]%  
```


### Description

Enable content specifically for Edit Mode or specifically for Preview/Publish Mode. 

Some content is not appropriate for display in Edit mode and other content is not appropriate for being published. You can limit the display of the content to a specific mode by using conditionals. You can use conditionals in any type of template (HTML, CSS, JS, etc.). Using a conditional to disable the display of certain elements with CSS is a good way to keep the user focused on the content that needs to be edited.

 > Warning: Do not place conditionals around editable content or containers (i.e. don't wrap %slice%, %text%, or %html% in a conditional.

#### Example 1: disable fancy CSS in edit mode for speed.

```css
#%id% .fancyStuff {  
  %[if edit]%  
    display:none;  
  %[endif]%

  %[if !edit]%  
    display:block;  
  %[endif]%  
}  
```


#### Example 2:  enable some HTML only for preview and publish

```html
%[if !edit]%
  <span>This will not appear in edit mode!</span>
%[endif]%
```










