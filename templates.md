---
title: Template Variables
layout: page
back:
  - top: /bundle
---


### Overview
Templates are files that define the content of your stack. You can have any number of templates in your stack. They're specified in the Info.plist [Templates Dictionary](templates-dictionary).  The tempalte variables listed below will be replaced in each template.

> Note: not every template variable is available in every template. For example: page-scoped templates cannot utilize properties and control template variables.




___
### Contents

##### Basic Containers
  * [Styled Text Container][] — *A general purpose text container.*
  * [Plain Text Container][] — *An HTML stack.*
  * [Image Container][] — *An image stack.*
  * [Stack Container][] — *A container for other stacks (a.k.a a one column stack).*

##### Paths
  * [Asset Path][] — *The path to the your stack's assets.*
  * [Site Asset Path][] — *The path to assets shared site-wide.*
  * [RapidWeaver Asset Path][] — *The path to the RapidWeaver Resources/Assets folder.*

##### Properties and Controls
  * [Stack Instance ID][] — *The ID of the current stack.*
  * [Property Value][] — *Properties from controls.*
  * [Color Property Values][] — *Color controls and Color-Math.*
  * [Link Property Value][] — *Link controls and their properties.*

##### Expressions and Conditionals
  * [Conditionals][] — *Conditional content based on stack properties.*
  * [Integer Comparison][] — *Compare integers and booleans.*
  * [Integer Math][] — *Simple math.*
  * [String Comparison][] — *Compare strings for equality.*
  * [Conditional Display][] — *Enable content only for Edit or Publish.*

##### Special
  * [Repeating Blocks][] — *Repeating content. Please see warnings before using.*
  * [Reserved][] — *Reserved for internal use.*



___
### Reference
___
<style>hr {margin:50px 0;}</style>

[Asset Path]: #AssetPath
<a name='AssetPath'></a>
#### Asset Path

`%assetPath%`

##### Description
This keyword will be replaced by the path to Stacks' assets directory for the page.  This will be needed to link to assets that have been included in plist. For more information about assets see: the [Asset Dictionary documentation](/assets-dictionary).

##### Available: Stacks API v2  



___
[Color Property Values]: #ColorPropertyValues
<a name='ColorPropertyValues'></a>
#### Color Property Values
Color math allows templates variable to be replaced by colors that are modified from the user-selected custom-item generated colors.

##### Description
Color math works in the templates by adding an operator after the id name of template.

##### Example
```
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
##### Available: Stacks API v3



___
[Conditional Display]: #ConditionalDisplay
<a name='ConditionalDisplay'></a>
#### Conditional Display
 
```
%[if edit]%  
%[endif]%  
```
or
```
%[if !edit]%  
%[endif]%  
```


##### Description
Enable content specifically for *Edit Mode* or specifically for *Preview/Publish Mode*.  
Some content is not appropriate for display in Edit mode and other content is not appropriate for being published.  You can limit the display of the content to a specific mode by using conditionals.  You can use conditionals in any type of template (HTML, CSS, JS, etc.).  Using a conditional to disable the display of certain elements with CSS is a good way to keep the user focused on the content that needs to be edited.

> Warning: Do not place conditionals around editable content or containers (i.e. don't wrap `%slice%`, `%text%`, or `%html%` in a conditional.

##### Example 1 *— CSS Template*
In the CSS template used to disable the fancy styles:

```
#%id% .fancyStuff {  
  %[if edit]%  
    display:none;  
  %[endif]%

  %[if !edit]%  
    display:block;  
  %[endif]%  
}  
```

##### Example 2 *— HTML Template*
In an HTML template, used to enable content only for publishing:
```
%[if !edit]%
  <span>This will not appear in edit mode!</span>
%[endif]%
```

##### Available: Stacks API v2




___
[Conditionals]: #Conditionals
<a name='Conditionals'></a>
#### Conditionals
Conditionals allow you to add or remove content based on the value of a property or and expression.

##### Description
Conditionals allow you to add or remove content to the generated HTML based on the value of the conditional argument.  
Conditionals may be nested.

##### Syntax

```
%[if <expression>]%
    content displayed when <expression> is true
%[endif]%
```
or
```
%[if <expression>]%
        content displayed when <expression> is true
%[else]%
    content displayed when <expression> is false
%[endif]%
```
 * `<expression>` can be integer or boolean [property](#PropertyValue) (e.g. `%id=checkBoxValue%`) or an [expression](#IntegerMath) that evaluates to an integer or boolean (e.g. `%( %id=count% < 1 )%`).  
 Integer values are converted to boolean using the C language rules (e.g. 0 => False, all other values => True).

##### Available: Stacks API v3



___
[Image Container]: #ImageContainer
<a name='ImageContainer'></a>
#### Image Container

Simple form:
```
%image%
```

With preset values:
```
%image imageScaleMode=1 imageMaxWidth=100 imageMaxHeight=100%
```

* default properties - Default values for the image editing properties can be included.  Any of the properties defined for the Image Transform control may be used.  
Note:  default properties are not immutable. The user can change these by editing the image. For immutable image modifications use an Image Transform.
***(Available: Stacks API 3+)***

##### Description
A simple image container.  This is the image stack.

##### Available: Stacks API v1



___
[Integer Comparison]: #IntegerComparison
<a name='IntegerComparison'></a>
#### Integer Comparison
Simple number comparisons for integers and booleans.

`%([!] <argument1> <operator> <argument2> )%`

 * `!` will perform a logical NOT on the output of the operation
 * `<argument1>` and `<argument2>` can be any integer value or any property that evaluates to an integer value. ***Behavior with non-integer values is undefined.***
 * `<operator>` can be any of: `==, !=, <, <=, >, >=`
 * Operators have C language functions.
 
##### Description
Inline functions for evaluating simple integer comparisons. The syntax is identical to [Integer Math](#IntegerMath). Statements can be nested, but ***must contain only two arguments***.

##### Example
evaluates to 1 when count is 0 or less  
`%( %id=count% < 1 )%`  

evaluates to 1 when the slider value is greater than 99
`%( %id=slider% >= 100 )%`  

##### Available: Stacks API v3



___
[Integer Math]: #IntegerMath
<a name='IntegerMath'></a>
#### Integer Math
Simple inline math for integers and booleans.

##### Syntax

`%([!] <argument1> <operator> <argument2> )%`

 * `!` will perform a logical NOT on the output of the operation
 * `<argument1>` and `<argument2>` can be any integer value or any property that evaluates to an integer value. ***Behavior with non-integer values is undefined.***
 * <operator> can be any of: `+, -, *, &&, ||, >>, <<`
 * Operators have C language functions.

##### Description
Inline functions for evaluating simple integer functions. The syntax is identical to [Integer Comparison](#IntegerComparison). Statements can be nested, but ***must contain only two arguments***.

##### Example
evaluates to 2
`%(1+1)%`

evaluates to 0
`%( %(1+1)% - %(1+1)% )%`

evaluates to true only if both enables are true
`%( %id=enable1% && %id=enable2% )%`  <!-- will be replaced by 1 only if both enables are true -->

evaluates to 12
`%( 25 >> 1 )%`
    
> Note: Since this is integer-only math, there is no divide operator.  However the shift-right operator can provide a divide-by-two (see last example).

##### Available: Stacks API v3



___
[Link Property Value]: #LinkPropertyValue
<a name='LinkPropertyValue'></a>
####Link Property Value
The values of a link property can be used in two ways: to create the opening of an anchor tag, or to retrieve only one part (such as the href URL).

##### Anchor Tag Syntax

`%id=my_link_ID%`

 * *my_link_ID* — The property ID of the link control.

The anchor tag syntax replaces the templates with the first half of an anchor tag.
> Example:  If a user enters the link `http://apple.com` and specifies a `rel` property of `Mother Ship` the replacement will be:

`<a href="http://apple.com" rel="Mother Ship">`

It will be up to the stack designer to provide the body of the anchor tag (the text inside the tag) and the closing </a> as well.

> Note: The Link Control will always return a valid link, even when the user has not entered a link. This is to ensure that your closing </a> will always be balanced. If you need to remove a link you should do so with a separate enable control and other logic within your stack.


##### Property Syntax

`%id=my_link_ID -property_name%`

 * *my_link_ID* — The property ID of the link control.
 * *property_name* - The link property to return (e.g. `href`).

The alternate usage of a link is to extract a specific property such as the href or rel property and replace the template with only that.
> Example:  If a user enters the link `http://apple.com` and specifies a `rel` property of `Mother Ship` the replacement will be:

`%id=my_link_ID -href%`

the replacement will be:

`http://apple.com`

##### Available: Stacks API v3



___
[Plain Text Container]: #PlainTextContainer
<a name='PlainTextContainer'></a>
#### Plain Text Container

%html%

%html="*default_text*"%

 * default_text - a string of characters that will be the default text provided to the user when a new plain text stack is added to a page.  ***(Available: API 2+)***

##### Description
A plain text container. This is the core of an HTML stack.

##### Available: Stacks API v1



___
[Property Value]: #PropertyValue
<a name='PropertyValue'></a>
#### Property Value

`%id=property_id%`

 * *property_id* - The name of the property to return.

##### Description
This template returns the value of a property. Properties and their corresponding controls are defined in the [Info.plist](/info-plist) file.  When a user changes the properties by adjusting the controls, this value will change in real time.

##### Available: Stacks API v2



___
[RapidWeaver Asset Path]: #RapidWeaverAssetPath
<a name='RapidWeaverAssetPath'></a>
#### RapidWeaver Asset Path

%rapidweaverAssetPath%

##### Description
Returns the the path to the RapidWeaver Resources/Assets directory.  This will be needed to link to assets that the user has included in the Page Inspector window in RapidWeaver.

> Note: Stacks **can not** publish stack assets (like those described in the [Asset Dictionary documentation](/assets-dictionary)) to the RapidWeaver asset path.

##### Available: Stacks API v2



___
[Repeating Blocks]: #RepeatingBlocks
<a name='RepeatingBlocks'></a>
#### Repeating Blocks

using a constant with a repeatIndex
```
%[repeat 4]%
<h2>%id=repeatIndex%</h2>
%[endrepeat]%
```

using a property with a slice as the content
```
%[repeat my_slider_ID]%
%slice%
%[endrepeat]%
```

##### Description
The repeat block will repeat the contents between the *repeat* and *endrepeat* keywords.  The block can either be repeated a fixed number of times by using an integer or a variable number of times by using a property ID.

Inside of the repeat block a special custom variable will be active.  The "repeatIndex" variable will be replaced by the index of the repeated content.  The index will start at 0 and increment to (n-1).  
You **can** include %slice% %text% or any other template variables inside the repeating block.  
You **can** nest repeat blocks.

> <span style='color:red'>Warning: Repeat blocks come with a significant CPU cost.  To make your stack perform well, keep your repeat blocks as simple as possible and limit the count.  Repeat blocks are included in the API because there are currently some problems that cannot be solved without them -- but you are urged to find other solutions and use this only as a last resort.</span>

##### Available: Stacks API v2



___
[Reserved]: #Reserved
<a name='Reserved'></a>
#### Reserved

%stack%

##### Description
This is an internal reserved template, it should not be used. It's use in 3rd party stacks is undefined and will change in future versions.



___
[Site Asset Path]: #SiteAssetPath
<a name='SiteAssetPath'></a>
#### Site Asset Path

%siteAssetPath%

##### Description
Returns the path to the assets directory shared by all pages of the site.  This will be needed to link to assets that have been included as site assets. For more information about assets see: the [Asset Dictionary documentation](/assets-dictionary).

##### Available: Stacks API v2



___
[Stack Container]: #StackContainer
<a name='StackContainer'></a>
#### Stack Container

%slice%

##### Description
A generic stack container (the Drop Stacks Here). This is the core of the One Column stack.

##### Available: Stacks API v1



___
[Stack Instance ID]: #StackInstanceID
<a name='StackInstanceID'></a>
#### Stack Instance ID

%id%     

***(Available: Stacks API 2+)***

##### Description
This keyword will be replaced by the HTML DOM id of inner element of the stack's wrapper divs.  This is the id of the "stacks_in" element.
> Warning: Do not modify the CSS properties that the use sets such as border, margin, and padding.  Doing so will confuse the user and may cause display inconsistencies in the Stacks edit mode user interface.

##### Available: Stacks API v2



___
[String Comparison]: #StringComparison
<a name='StringComparison'></a>
#### String Comparison
Inline string comparison.

##### Syntax

`%( "<string1>" <operator> "<string2>" )%`

 * `<string1>` and `<string2>` can be any string or any property that evaluates to a string. Strings must be surrounded by double quotes.
 * Whitespace within the quotes is treated literally.
 * Whitespace outside of the quotes is ignored.
 * `<operator>` can be any of: `==, !=`
 * operators have the C language functions.

##### Description

Inline string comparison operations can evaluate equality of strings. The output of the operation is a boolean true or false, so this can be used in combination with [Integer Math](#IntegerMath).

##### Example

evaluates to false
`%("Red"=="Blue")%`

evaluates to true unless the user selects the droid you were looking for from the popup
`%( "%id=mySelect%" != "DroidYouLookedFor" )%`

evalutes to true for Yoda
`%( %( %( "%id=value%" == "Do" )% || %( "%id=value%" != "Do" )% )% && %( "%id=value%" != "Try" )% )%`

##### Available: Stacks API v3



___
[Styled Text Container]: #StyledTextContainer
<a name='StyledTextContainer'></a>
#### Styled Text Container

%text%

%text="*default_text*"%

 * default_text - a string of characters that will be the default text provided to the user when a new stack is dragged to the page.  ***(Available: API 2+)***

##### Description
A basic Styled Text container. This is the core of the Text stack.

##### Available: Stacks API v1









