---
name: macOS Version
syntax: "%macOSVersion%"
group: properties and controls
description: The version number of macOS
available: 13

---



### Usage

```html
%macOSVersion%
```


### Description

This is replaced with the version number of macOS that is running Stacks.
This the the human readable version number as apposed to the build number.

At the time of this writing the current version of macOS Ventura is "13.2.0".

#### Example

- Input:

```
The user is running macOS version v%macOSVersion%.
```

- Output: 

The user is running macOS version v13.2.0.


#### Not for Conditionals

This template is designed just for display to users, not conditional code.
If you need to use the macOS version number in a conditional you may want 
to consider using a different template instead.
There are four other templates that return the version number in a way that is easier 
to use in a conditional statement:

##### Related Templates for Conditionals

- [%macOSVersionAsInteger%](/templates/macOSVersionAsInteger/)
- [%macOSMajorVersion%](/templates/macOSMajorVersion/)
- [%macOSMinorVersion%](/templates/macOSMinorVersion/)
- [%macOSPatchVersion%](/templates/macOSPatchVersion/)


#### A Note About Big Sur

It should be noted that macOS/Mac OS X, versions and naming both shift in an unexpected way at macOS Big Sur. 

#### The macOS Names and Versions

| macOS Name           | Version Number |
| :---                 |     ---:       |
| Mac OS X Sierra      |  10.12.0       |
| Mac OS X High Sierra |  10.13.0       |
| Mac OS X Mojave      |  10.14.0       |
| Mac OS X Catalina    |  10.15.0       |
| macOS Big Sur        |  11.0.0        |
| macOS Monterey       |  12.0.0        |
| macOS Ventura        |  13.0.0        |



