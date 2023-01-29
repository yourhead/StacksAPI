---
name: macOS Patch Version
syntax: "%macOSPatchVersion%"
group: properties and controls
description: The patch (third) component of the macOS version
available: 13

---



### Usage

```html
%macOSPatchVersion%
```


### Description

This is replaced with the patch component of the macOS version. The patch component is the third and last of the three
components of the macOS version. As an example, the current version as of this writing is macOS `13.0.2`, so the *major* compoent
is `13`, the *minor* component is `0`, and the *patch* component is `2`. This template would be replaced by `2`.

This is not meant to be a human readable value, if you need the full human readable macOS version you should use 
[%macOSMajorVersion%](../macOSVersion/) instead.

The value returned is an integer, so this template works well as part of a conditional statement or a math expression.

If you need to compare to a specific version of macOS, you might also consider using
[%macOSVersionAsInteger%](../macOSVersionAsInteger/) instead which is perfect for doing version comparisons.

#### Example

- Input:

```

You are running

%[if %( %macOSPatchVersion% > 0 )% ]% 
    a patched version of macOS after the first release.
%[else]%
    the very first release of this version of macOS.
%[endif]%

```

- Output on a machine running macOS Ventura: 

You are running a patched version of macOS after the first release.


#### A Note About Big Sur

It should be noted that macOS/Mac OS X, versions and naming both shift in an unexpected way at macOS Big Sur.
The major component didn't increment for many years. 
All versions prior to and including Big Sur had the major version of 10.
After Big Sur the major version always increments and is one bigger than the year before.
Below is a list of the versions, names, and associated components.

#### The macOS Names and Versions

| macOS Name           | Version Number | Major | Minor | Patch |
| :---                 |     ---:       |  ---: |  ---: |  ---: |
| Mac OS X Sierra      |  10.12.0       | 10    | 12    | 00    |
| Mac OS X High Sierra |  10.13.0       | 10    | 13    | 00    |
| Mac OS X Mojave      |  10.14.0       | 10    | 14    | 00    |
| Mac OS X Catalina    |  10.15.0       | 10    | 15    | 00    |
| macOS Big Sur        |  11.0.0        | 11    | 00    | 00    |
| macOS Monterey       |  12.0.0        | 12    | 00    | 00    |
| macOS Ventura        |  13.0.0        | 13    | 00    | 00    |

