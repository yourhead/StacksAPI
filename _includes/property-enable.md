Hide or show the control based on the value of another property.

Enables allow a stack to show only the controls needed by the user to achieve a specific task.

The enable dictionary defines the ID of another control and the value that other control must equal. When the other control's value is not equal to the provided value, this control is hidden.

#### Enable Dictionary
 * `id` *(string)* — the ID of another control on which this control (Popup Menu) should depend.
 * `value` *(any type)* — when the value of the other control is equal to this value, this control is displayed, otherwise it is hidden.
 * `index` *(number)* - for arrayed controls you'll need to specify the index of the array id.
 * `round` *(boolean)* - whether or not to round numeric control values. the default is YES. you *must* set this value to NO to disable -- even if the property that's being matched has rounding enabled.
 * `operation` *(string)* - can be any of the following: `==`, `<`, `<=`, `>`, `>=`, `contains`, `matches`, or `caseInsensitiveMatches`.

#### Enable Operations
 * `==` - *(any type)* - ***default*** compares any two values. to maintain backwards compatibility rounding is never applied. *(aliases: `=`, `equals`, `equalTo`)*
 * `!=` - *(any type)* - compares any two values are not the same. *(aliases: `notEqual`, `notEqualTo`)*
 * `<` - *(number)* - less than. *(aliases: `lessThan`)*
 * `<=` - *(number)* - less than or equal to. *(aliases: `lessThanOrEqualTo`, `lessThanOrEquals`)*
 * `>` - *(number)* - greater than. *(aliases: `greaterThan`)*
 * `>=` - *(number)* - greater than or equal to. *(aliases: `greaterThanOrEqualTo`, `greaterThanOrEquals`)*
 * `contains` - *(string)* - This does a *case insensitive* match of the value anywhere in the string.
 * `doesntcontain` - *(string)* - This is the opposite of the `contains` operation.
 * `matches` - *(string)* - Wildcard match. Examples: `Red` (matches: `Red` and `Reddish`), `R?d` (matches: `Red` and `Rad` )
 * `doesntmatch` - *(string)* - This is the opposite of the `matches` operation.
 * `caseInsensitiveMatches` - *(string)* - Similar to `matches` but ignores case.
 * `caseInsensitiveDoesntMatch` - *(string)* - This is the opposite of the `caseInsensitiveMatches` operation.


> **Warning**: creating infinite loops in enable dependencies has undefined behavior. It will likely result in a RapidWeaver crash.

> NB: macOS does not specify the wildcard characters available or how they function. `*` and `?` clearly work as they do in a UNIX shell. you'll just have to guess at the rest.
