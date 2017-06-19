---
name: Conditional Display
syntax: "%%[if edit]%%  %%[endif]%%"
group: expressions and conditionals
description: Enable content only for Edit, Preview, or Publish.
available: 10

---



### Usage

```html
%%[[if <mode>]]%%  
    any content
%%[[endif]]%%  
```

or

```html
%%[[if !<mode>]]%%  
    any content
%%[[endif]]%%  
```

 - `<mode>` can be one of: `edit`, `preview`, or `publish`.


### Description

Enable content specifically for Edit, Preview, or Publish Mode. 

Some content is not appropriate for display in Edit mode and other content is not appropriate for being published. You can limit the display of the content to a specific mode by using conditionals. You can use conditionals in any type of template (HTML, CSS, JS, etc.). Using a conditional to disable the display of certain elements with CSS is a good way to keep the user focused on the content that needs to be edited.

> Note: Prior to Stacks 3.5 the sytax of the preprocessor macros was slightly different. Each macro was bounded by only one percent sign and one square-bracket. Old-style conditionals are still acceptable but are deprecated.

#### Example 1: disable fancy CSS in edit mode for speed.

```
#%id% .fancyStuff {  
  %%[[if edit]]%%  
    display:none;  
  %%[[endif]]%%

  %%[[if !edit]]%%  
    display:block;  
  %%[[endif]]%%  
}  
```


#### Example 2:  enable some HTML only for preview and publish

```html
%%[[if !edit]]%%
  <span>This will not appear in edit mode!</span>
%%[[endif]]%%
```




#### Example 3:  enable some HTML only for publish and the rest only for preview

```html
%%[[if publish]]%%
  <span>This will appear in publish mode!</span>
%%[[endif]]%%

%%[[if preview]]%%
  <span>This will appear in preview mode!</span>
%%[[endif]]%%
```










