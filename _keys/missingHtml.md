---
name: Missing Html
key: missingHtml
type: String
group: content
description: Content provided when this stack is missing
available: 10

---

When a stack that is being used in a project gets uninstalled for any reason (becomes missing), the Missing HTML is displayed in place of the stack's usual content.

You should provide a very simple message to help the user re-download the stack and get it installed again. Or to help them
get in touch with your support email to get a new download link.

The Missing HTML must be entirely self contained. Since it will only be displayed when the stack is missing, none of the usual templates, HTML, CSS, or assets will be available. This HTML and the [Missing URL](missingURL) will be the only info displayed. You will not have access to your usual plist values because the plist will be missing too.

Because this content is copied into the project file, you should try to keep it simple and small. Adding large inline images will slow down your stack.


 - The content **CAN** contain HTML and inline CSS.
 - The content **CANNOT** run any Javascript. It will be displayed in Edit Mode where Javascript is always disabled.
 - The content **CANNOT** rely on any other portion of your stack. It must be completely self contained.


> If the Missing HTML plist entry is NOT provided Stacks will automatically generate a short message for you. This message may contain some of the other information your stack provides, like the [Info URL](infoURL). However, it's best give users a friendly message to help them get their stacks installed again or get in touch with your support email to get a new download link.
