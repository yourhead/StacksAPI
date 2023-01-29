---
name: macOS Version As Integer
syntax: "%macOSVersionAsInteger%"
group: properties and controls
description: The version number of macOS as an integer
available: 13

---



### Usage

```html
%macOSVersionAsInteger%
```


### Description

This is replaced with an integer value based on the currently running version of macOS.
This is not meant to be a human readable version and should *never* be displayed as output to the user anywhere inside Stacks.

The primary use case for this template is within a condtional statement to enable or disable some other code. This integer follows
a simple pattern that such that each version of macOS has a corresponding, easy to predict integer value. The integer value always 
increases and never decreases (monotonically increasing). Here's how it works:

Each component of the version number corresponds to two digits in the integer. So the version number of `13.5.12`, which has components
of `13`, `5`, and `12` (the *major*, *minor*, and *patch* components), corresponds to an integer of `130512`.

A more mathematical definition of the integer is:

```
(10000 * major_version) + (100 * minor_version) + (patch_version)
```

#### Example

- Input:

```

You are running

%[if %( %macOSVersionAsInteger% >= 132000 )% ]% 
    macOS Ventura, the latest macOS version.
%[else]%
    an older version of macOS. Time for an update!
%[endif]%

```

- Output on a machine running macOS Ventura: 

You are running macOS Ventura, the latest macOS version.


#### Difficult to Parse

Although it's possible to parse this integer to assertain a specific component of
the macOS version, there may be simpler templates that can do the job faster. The
macOS version components are available separated out into three integers.
This may be easier, simpler, and more performant than trying to perform math on this template.
See the list below for the components.


##### Related Templates for Conditionals

- [%macOSMajorVersion%](/templates/macOSMajorVersion/)
- [%macOSMinorVersion%](/templates/macOSMinorVersion/)
- [%macOSPatchVersion%](/templates/macOSPatchVersion/)


#### A Note About Big Sur

It should be noted that macOS/Mac OS X, versions and naming both shift in an unexpected way at macOS Big Sur.
The major component didn't increment for many years. 
All versions prior to and including Big Sur had the major version of 10.
After Big Sur the major version always increments and is one bigger than the year before.
Below is a list of the versions, names, and associated integer values.

#### The macOS Names and Versions

| macOS Name           | Version Number | Inteter Value |
| :---                 |     ---:       |          ---: |
| Mac OS X Sierra      |  10.12.0       |        101200 |
| Mac OS X High Sierra |  10.13.0       |        101300 |
| Mac OS X Mojave      |  10.14.0       |        101400 |
| Mac OS X Catalina    |  10.15.0       |        101500 |
| macOS Big Sur        |  11.0.0        |        110000 |
| macOS Monterey       |  12.0.0        |        120000 |
| macOS Ventura        |  13.0.0        |        130000 |



