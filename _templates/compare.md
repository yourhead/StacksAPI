---
name: Integer Comparison
syntax: "%( A == B )%"
group: expressions and conditionals
description: String comparison operations.
available: 3

---


### Usage

```html
%([!] <argument1> <operator> <argument2> )%
```


 - `!` will perform a logical NOT on the output of the operation
 - `<argument1>` and `<argument2>` can be any integer value or any property that evaluates to an integer value. Behavior with non-integer values is undefined.
 - `<operator>` can be any of: `==, !=, &lt;, <=, >, >=`
 - Operators have C language functions.


### Description

Inline functions for evaluating simple integer comparisons. The syntax is identical to Integer Math. 

 > Note: Statements can be nested, but **must contain only two arguments**.

#### Example 1: compare a property to a literal number

evaluates to 1 when count is less than 1

```
%( %id=count% < 1 )%
```

#### Example 2: using a math expression to combine compares

evaluates to 1 when the slider value between 0 and 100

```
%( %( %id=slider% > 0 )% || %( %id=slider% < 100 )% )%
```
