---
name: Integer Math
syntax: "%( 1 + 2 )%"
group: expressions and conditionals
description: Simple math operations.
available: 3


---



### Usage

```html
%([!] <argument1> <operator> <argument2> )%
```

 - `!` will perform a logical NOT on the output of the operation
 - `<argument1>` and `<argument2>` can be any integer value or any property that evaluates to an integer value. Behavior with non-integer values is undefined.
 - `<operator>`can be any of: `+`, `-`, `*`, `&&`, `||`, `>>`, `<<``
 - Operators have C language functions.






### Description

Math operations for evaluating simple integer functions. The syntax is identical to [Integer Comparison](../compare). Statements can be nested, but **must contain only two arguments**.


#### Example 1: add to literal integers
evaluates to 2 

```
%( 1 + 1 )%
```

#### Example 2: nested operations
evaluates to 15

```
%( %( 1 + 2 )% - %( 3 * 4 )% )%
```

#### Example 3: logical operations
evaluates to true only if both enables are true 

```
%( %id=enable1% && %id=enable2% )%
```


#### Example 4: integer divide by 2
evaluates to 12 

```
%( 25 >> 1 )%
```

 > Note: Since this is integer-only math, there is no divide operator. However the shift-right operator can provide a divide-by-two (see last example).









