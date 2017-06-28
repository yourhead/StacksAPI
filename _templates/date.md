---
name: Date Values
syntax: "%id=dateID%"
group: properties and controls
description: Output of a date control.
available: 10


---



### Usage

```html
%id=<dateControlID>%
%id=<dateControlID> -format="<format>" %
%id=<dateControlID> -dateStyle="<short, medium, long, or full>" %
%id=<dateControlID> -timeStyle="<short, medium, long, or full>" %
```

 - `<dateControlID>` is the ID of a date control.
 - `<format>` a [Unicode Date Standard 35](http://unicode.org/reports/tr35/tr35-dates.html) format. There is a practical guide to these formats here: https://waracle.com/iphone-nsdateformatter-date-formatting-table/
 - `<short, medium, long, or full>` select a specific pre-formatted date that is localized to user's current macOS settings.



### Description

Output a long format full date/time string that is compatible with Moment.js (the default), a localized date or time style, or a specified date format.

> Note: date controls have been available since API v5, however the format and style parameters were introduced in API v10


#### Example 1: Long format date

template:

```html
    The UNIX date is: %id=dateProperty%
```

The UNIX date is: 2017-06-27T18:48:09CDT


#### Example 2: Short localized time

template:

```html
    The time is: %id=dateProperty -timeStyle="short"%
```

The time is: 7:25 PM
> This is in the US. In other locales it will appear formatted for that region.

#### Example 3: Full localized date

template:

```html
    The date is: %id=dateProperty -dateStyle="full"%
```

The date is: Tuesday, June 27, 2017
> This is in the US. In other locales it will appear formatted for that region.


#### Example 4: Long time and short date

template:

```html
    It is %id=dateProperty -timeStyle="long"% on %id=dateProperty -dateStyle="short"%
```

It is 6:48:09 PM CDT on 6/27/17


#### Example 5: Custom format

template:

```html
    This is the year %id=dateProperty -format="yyyy"%.
```

This is the year 2017.
