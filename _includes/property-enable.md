Hide or show the control based on the value of another property.

Enables allow a stack to show only the controls needed by the user to achieve a specific task.

The enable dictionary defines the ID of another control and the value that other control must equal. When the other control's value is not equal to the provided value, this control is hidden.

#### Enable Dictionary
 * `id` *(string)* — the ID of another control on which this control (Popup Menu) should depend.
 * `value` *(any type)* — when the value of the other control is equal to this value, this control is displayed, otherwise it is hidden.
 
> **Warning**: creating infinite loops in enable dependencies has undefined behavior but will likely result in a crash.