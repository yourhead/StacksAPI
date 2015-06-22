---
title: String Escaping
layout: page
back:
  - top: /templates
links:
  - top: /templates
---


## String Escaping
Stacks provides access to the RapidWeaver string escaping API. You can specify a specific string escaping format whenever you template replace a string from an "input" control (a text box).

*NB: The specific behavior of these encodings is controlled by Rapidweaver, not Stacks.*

### String Escape Types

* `-encodeJS` - Javascript  — Encoded for use inside a single-quoted string.
* `-encodePHP` - PHP  — Encoded for use inside a single-quoted string.
* `-encodeHTML` - HTML  — Encoded for display on an HTML page (markup characters are hexadecimal encoded).
* `-encodeHTMLAttribute` - HTML Attribute  — Encoded for use inside a double quoted HTML attribute (e.g. `target="blank"`).
* `-encodeXML` - XML  — Encoded for use inside XML strings.
* `-encodeFilename` - Filename  — Encoded for use as a file name on most filesystems.


#### Example 1: showing various outputs using various encodings

We start this example with a text control `id=textInput` containing the following text with some special characters

```
this is a test " ' < > $
```


If we out the text with the various encoudings like this:

```html
text (default):   %id=textInput%
text (JS):        %id=textInput -encodeJS%
text (PHP):       %id=textInput -encodePHP%
text (HTML):      %id=textInput -encodeHTML%
text (Attribute): %id=textInput -encodeHTMLAttribute%
text (XML):       %id=textInput -encodeXML%
text (Filename):  %id=textInput -encodeFile%
```

This output will be produced:

```html
text (default):   this is a test " ' < > $
text (JS):        this is a test " \' < > $
text (PHP):       this is a test " \' < > $
text (HTML):      this is a test &#34; &#39; &#60; &#62; $
text (Attribute): this is a test &#34; &#39; &#60; &#62; $
text (XML):       this is a test &#34; &#39; &#60; &#62; $
text (Filename):  this-is-a-test-0022-0027-003C-003E-0024
```

