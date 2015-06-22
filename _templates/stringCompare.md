---
name: String Comparison
group: expressions and conditionals
description: String comparison operations.
available: 3

---



### Usage

```html
%( "<string1>" <operator> "<string2>" )%
```

 - `<string1>` and `<string2>` can be any string or any property that evaluates to a string. Strings must be surrounded by double quotes.
 - Whitespace within the quotes is treated literally.
 - Whitespace outside of the quotes is ignored.
 - `<operator>` can be any of: `==`, `!=`
 - operators have the C language functions.


### Description

Inline string comparison operations can evaluate equality of strings. The output of the operation is a boolean true or false, so this can be used in combination with [Integer Math](../math).

#### Example 1: compare to literal strings.
evaluates to `false`:

```
%("Red"=="Blue")%
```

#### Example 2: compare a property with a literal string
evaluates to `true` unless the user selects the droid you were looking for from the popup:

```
%( "%id=mySelect%" != "DroidYouLookedFor" )%
```

#### Example 3: compare a property with a literal string
evalutes to `true` especially for Yoda 

```
%( 
   %( 
      %( "%id=value%" == "Do" )% || 
      %( "%id=value%" != "Do" )% 
   )% && 
   %( "%id=value%" != "Try" )% 
)%
```







