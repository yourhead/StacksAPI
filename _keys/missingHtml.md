---
name: Missing Html
key: missingHtml
type: String
group: content
description: Content provided when this stack is missing
available: 10

---

When this stack becomes uninstalled but is still being used in a file this content will be displayed to the user.

This should be a simple message that helps them re-download and re-install the stack.

 - The content CAN contain HTML and inline CSS.
 - The content CANNOT contain Javascript. It will be displayed in Edit Mode where Javascript is disabled.
 - The content CANNOT rely on any other portion of your stack. It must be completely self contained.

> If not content is provided a simple short message will be provided.
