---
name: Repeating Blocks
syntax: "%[repeat]% %[endrepeat]%"
group: special
description: Repeating Content. Please see warnings before using.
available: 2

---



### Usage

```html
%[repeat 4]%
<h2>%id=repeatIndex%</h2>  
%[endrepeat]%
using a property with a slice as the content
```

or

```html
%[repeat my_slider_ID]%
%slice%
%[endrepeat]%
```


### Description

The repeat block will repeat the contents between the repeat and endrepeat keywords. The block can either be repeated a fixed number of times by using an integer or a variable number of times by using a property ID.

Inside of the repeat block a special custom variable will be active. The "repeatIndex" variable will be replaced by the index of the repeated content. The index will start at 0 and increment to (n-1). 

You can include %slice% %text% or any other template variables inside the repeating block. 

You can nest repeat blocks.

 > <span style='color:red !important;'>Warning: Repeat blocks come with a significant CPU cost. To make your stack perform well, keep your repeat blocks as simple as possible and limit the count. Repeat blocks are included in the API because there are currently some problems that cannot be solved without them -- but you are urged to find other solutions and use this only as a last resort.</span>

