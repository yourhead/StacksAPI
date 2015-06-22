---
name: Plain Text Container
syntax: "%html%"
description: The content of an HTML stack.
available: 1

---



### Usage

```html
%html%
```

or 

```html
%html="<default_text>"%
```

 - `<default_text>` - a string of characters that will be the default text provided to the user when a new plain text stack is added to a page. *(Available: API 2+)*

### Description

A plain text container. This is the core of an HTML stack.

Text may be escaped for the various languages associated with the web.  You use the `-ecocodeHTML` switch to ampersand encode all the HTML entities.  There are [many formats and more details are list here]({{site.baseurl}}/stringEscaping).

