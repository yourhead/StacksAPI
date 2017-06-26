---
name: Tags
key: tags
type: Array
value: An array of tags
description: Tags used for search and groups.
available: 7
---

This key should be set to a small array of strings used to aid in search. When the user searches for stacks the tags will be searched too. The user can also click on tags to find all stacks with the same tag.

When the user chooses to organize their library by group (the default) the first tag will be used as the group name.

You can provide any number of tags, but only the first few will be displayed in the UI. Short, simple, commonly used words make the best tags.

If no tags are provided, Stacks will fall back to the v6 API and use the group (if provided) as the only tag.


#### The purpose of tags

The purpose of a tag is to help the user organize their library by common tasks, or common stack functions.  You can provide tags for anything, Stacks may ignore, or give the user the preference to ignore, some tags that are innappropriate or unhelpful.



#### Author names in tags

Stacks 3 provides users with a mechanism for arranging by author if they wish to and search always includes the author. This means when they've chose to arrange their library by tag they **DO NOT want to arrange by author**. Please respect that customer desire and do not put make the first tag you author name.

Stacks 3 will may to include features that help the user organize their library they want it to be organized and ignore developers who try to "game/hack/override" the system.
