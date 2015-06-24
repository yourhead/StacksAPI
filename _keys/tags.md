---
name: Tags
key: tags
type: array
value: An array of tags
description: Tags used for search and groups.
available: 7
---

This key should be set to a small array of strings used to aid in search. When the user searches for stacks the tags will be searched too. The user can also click on tags to find all stacks with the same tag.

When the user chooses to organize their library by group (the default) the first tag will be used as the group name.

You can provide any number of tags, but only the first few will be displayed in the UI. Short, simple, commonly used words make the best tags.

If no tags are provided, Stacks will fall back to the v6 API and use the group (if provided) as the only tag.