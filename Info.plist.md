<style>
h4 em {font-weight:normal;}
</style>

### Overview
The Info.plist file within a stack defines the basic attributes of the stack like its title and version number, the custom properties the stack will display when selected, and file names of each of the templates and assets.





### Contents

#### Basic
  * [ID][] — *CFBundleIdentifier*
  * [Title][] — *title*
  * [Group][] — *group*
  * [Icon Name][] — *icon*
  * [Version][] — *CFBundleShortVersionString*

#### Content
  * [Templates][] — *templates*
  * [Custom Properties and Controls][] — *customItems*
  * [Assets][] — *assets*

#### URLs
  * [Information URL][] — *infoURL*
  * [Help URL][] — *helpURL*

####Javascript
  * [Javascript Library][] — *javascriptLib*
  * [Javascript Closure Disable][] — *javascriptClosure*

####php
  * [php File Extension Enable][] — *requiresPhp*
  * [php Session Enable][] — *requiresPhpSession*
  * [php Buffer Enable][] — *requiresPhpBuffer*

####Version
  * [Sparkle Appcast URL][] — *SUFeedURL*
  * [Minimum Stacks API Version][] — *minAPIVersion*







### Reference

___
[Assets]: #Assets
<a name='Assets'></a>
####Assets *— assets*
 * *Key* <br> assets
 * *Type* <br> Array
 * *Value* <br> An array of asset file dictionaries. See [the asset dictionary page](Stacks API Asset Dictionary) for more info.
 * *Optional*

#####Description
An array of asset files declarations.  
A stack may include other files and folders that to be exported.  Each asset will be exported as-is, without templating, HTML conversion, or image optimization.  Folders will be exported with all of their files (there is no need to declare each file within the folder).  Each item in the array corresponds to a file and is a dictionary.  See [the asset dictionary page](Stacks API Asset Dictionary) for more info.

> Note: It's up to you to ensure that the items have acceptable web-friendly naming and do not conflict with other files that might be present in other elements.

#####Available: Stacks API v2



___
[Custom Properties and Controls]: #CustomPropertiesandControls
<a name='CustomPropertiesandControls'></a>
####CustomPropertiesandControls *— customItems*
 * *Key* <br> customItems
 * *Type* <br> Array
 * *Value* <br> An array of custom property dictionaries. See [the custom property dictionary page](Stacks API Custom Property Dictionary) for more info.
 * *Optional*

#####Description
An array of custom property declarations.  
Each item in the custom properties array defines a property that you stack can use in its templates.  Most custom properties have a corresponding GUI control for the user to set the property.  When a stack in the layout is selected, the GUI controls for each custom properties are shown in the sidebar.  As the user changes the values, the template files for your stack are injected with the new values.  
For more information on the custom properties dictionaries and the corresponding GUI controls see [the custom property dictionary page](Stacks API Custom Property Dictionary) for more info.

#####Available: Stacks API v2



___
[Group]: #Group
<a name='Group'></a>
####Group *— group*
 * *Key* <br> group
 * *Type* <br>String
 * *Optional*

#####Description
The library group for your stack.
Stacks libraries are organized into groups.  You can specify the group your stack should be placed in by adding the group property.  A stack without a group will be placed into the "Other Stacks".

#####Available: Stacks API v3



___
[Help URL]: #HelpURL
<a name='HelpURL'></a>
####Help URL *— helpURL*
 * *Key* <br> helpURL
 * *Type* <br>String
 * *Optional*

#####Description
The URL for help and/or support for your stack.  
If an Help URL is present then the user will see an **Help** button in the detail view of the library.  When the user clicks the **Help** button they'll be shown the URL in their web browser.

#####Available: Stacks API v2



___
[Icon Name]: #IconName
<a name='IconName'></a>
####Icon Name *— icon*
 * *Key* <br> icon
 * *Type* <br> String
 * *Required*

#####Description
The base name of your stack's icon files.  
The library displays a smaller 50x50 pixel icon image in the grid view.  When a users selects your icon, it will display a 58x58 pixel image in the library detail view.  You must provide an icon file for each of these images.

Each icon file should be PNG format and have the .png extension.  A unique app-shaped icon with a transparent background is recommended.  The file names for the icons should be in the format:

`
<base_name>@<size>.png
`

`<base_name>` is the name that you provide in the property.  
`<size>` is the width of the image. Current supported sizes are: 50 and 58.

#####Example
In the plist file:  
`
<key>icon</key>  
<string>MyGreatIcon</string>
`

Files in the resources folder:  
`
MyGreatIcon@50.png  
MyGreatIcon@58.png
`

#####Available: Stacks API v5



___
[ID]: #ID 
<a name='ID'></a>
####ID *— CFBundleIdentifier (Bundle Identifier)*
 * *Key* <br>CFBundleIdentifier
 * *Human Readable Key* <br>Bundle Identifier
 * *Type* <br>String
 * *Required*

#####Description
The ID is the unique identifier for your stack. To ensure unqueness, it's recommended you use [reverse DNS format](http://en.wikipedia.org/wiki/Reverse-DNS).  
This should be a string consisting of just lowercase characters, periods, and underscores (***There should be no spaces in the ID***). It must uniquely identify your stack.  

> Note: This value is used to bind the user's content to your stack. For this reason **the ID must never change.**

#####Example
`
<key>CFBundleIdentifier</key>  
<string>com.mycompany.mystackname</string>
`
#####Available: Stacks API v1



___
[Information URL]: #InformationURL
<a name='InformationURL'></a>
####Information URL *— infoURL*
 * *Key* <br> infoURL
 * *Type* <br>String
 * *Optional*

#####Description
The URL for general information about your stack for the user.  
If an Info URL is present then the user will see an **Info** button in the detail view of the library.  When the user clicks the **Info** button they'll be shown the URL in their web browser.

#####Available: Stacks API v2



___
[Javascript Closure Disable]: #JavascriptClosureDisable
<a name='JavascriptClosureDisable'></a>
####Javascript Closure Disable *— javascriptClosure*
 * *Key* <br> javascriptClosure
 * *Type* <br> Boolean
 * *Optional*

#####Description
Javascript closures are enabled by default.  If you would like to disable them you can set this plist entry to false.

> Warning:  Please only disable closures if there is no alternative. Disabling closures will almost certainly cause incompatabilities with some RapidWeaver themes.

#####Available: Stacks API v2



___
[Javascript Library]: #JavascriptLibrary
<a name='JavascriptLibrary'></a>
####Javascript Library *— javascriptLib*
 * *Key* <br> javascriptLib
 * *Type* <br> String
 * *Value* <br> One of: `jQuery`, `MooTools`, or `jQuery UI`
 * *Optional*

#####Description
The Javascript base library to be included for the page.
Stacks will include a Javascript base library for all the stacks to share. There are three supported libraries:

* jQuery
* MooTools
* jQuery UI  ***(Available: Stacks API v3)***

The library will be included by using the Google AJAX Libraries API.  This is a convenient and reliable source of the most recently released versions of the libraries.  However it does come with some important implications:

#####Available: Stacks API v2



___
[Minimum Stacks API Version]: #MinimumStacksAPIVersion
<a name='MinimumStacksAPIVersion'></a>
####Minimum Stacks API Version *— minAPIVersion*
 * *Key* <br> minAPIVersion
 * *Type* <br>String
 * *Optional*

#####Description
The minimum API version required by your stack.
You can use the minimum version to detect a specific version of the API that your stack requires.  Values should be a simple integer of the major version number required.  If you are using the Stacks API 2.0 features, you should set the minAPIVersion to 2.

> Warning:  Only use a min API version if there is a known incompatibility.  Do not blindly add min limits.

#####Available: Stacks API v2



___
[php File Extension Enable]: #phpFileExtensionEnable
<a name='phpFileExtensionEnable'></a>
####php File Extension Enable *— requiresPhp*
 * *Key* <br> requiresPhp
 * *Type* <br> Boolean
 * *Optional*

#####Description
When set, the page will be exported with the .php file extension.  

#####Available: Stacks API v4



___
[php Session Enable]: #phpSessionEnable
<a name='phpSessionEnable'></a>
####php Session Enable *— requiresPhpSession*
 * *Key* <br> requiresPhpSession
 * *Type* <br> Boolean
 * *Optional*

#####Description
The php session enable.  
This will add the call to the php session_start function.  You can get more information about how to use php sessions and the session_start function on the [php reference page](http://www.php.net/manual/en/function.session-start.php).

#####Available: Stacks API v5



___
[php Buffer Enable]: #phpBufferEnable
<a name='phpBufferEnable'></a>
####php Buffer Enable *— requiresPhpBuffer*
 * *Key* <br> requiresPhpBuffer
 * *Type* <br> Boolean
 * *Optional*

#####Description
The php buffer enable.  
This will add the call to the php ob_start function.  You can get more information about how to use php output control and the ob_start function on the [php reference page](http://us2.php.net/manual/en/book.outcontrol.php).

#####Available: Stacks API v5



___
[Sparkle Appcast URL]: #SparkleAppcastURL
<a name='SparkleAppcastURL'></a>
####Sparkle Appcast URL *— SUFeedURL*
 * *Key* <br> SUFeedURL
 * *Type* <br>String
 * *Optional*

######Description
The URL used by the Sparkle automatic updater to locate the stack's update appcast.  
You can provide a URL to an XML appcast on your own server.  The appcast will be read and compared to the version information in the currently installed stack.  If the appcast version is newer, then the appcast info will be used to install the new version.  
You can find more information about creating an appcast and publishing an update on the [Sparkle website](http://wiki.github.com/andymatuschak/Sparkle/publishing-an-update).

> Note:  Setting up an appcast for the first time can be challenging.  There are many details required before it all begins to work.  Stacks will output some information about update failures to the developer log.  If you need help getting things set up please post of the [Stack Developers Group](http://groups.google.com/group/stack_developers?hl=en) with details and questions.  Others have been through the process and can offer some assistance.

#####Available: Stacks API 2



___
[Title]: #Title
<a name='Title'></a>
####Title *— title*
 * *Key* <br>title
 * *Type* <br>String
 * *Required*

#####Description
The title of your stack.  
The title is the displayed in the library so should be human readable. If your title is too long it may get truncated in some view modes, so please keep it short and simple.

#####Available: Stacks API v1



___
[Templates]: #Templates
<a name='Templates'></a>
####Templates *— templates*
 * *Key* <br> templates
 * *Type* <br> Array
 * *Value* <br> An array of template file dictionaries. See [the template dictionary page](Stacks API Template Dictionary) for more info. And see the [template variable page](Stacks API Template Variables) for more info on writing template files.
 * *Required — a stack must have at least one HTML template defined.*

#####Description
An array of template file declarations.  
Each entry in the Templates array is a dictionary that corresponds to a template file for your stack.  When the page is published each template in your stack is processed, each template variable within the template is replaced with the content or property for each stack.  
Each entry in the templates array should be a template dictionary. See [the template dictionary page](Stacks API Template Dictionary) for more info.  
To learn more about writing template files see the [template variable page](Stacks API Template Variables).

#####Available: Stacks API v5



___
[Version]: #Version
<a name='Version'></a>
####Version *—CFBundleShortVersionString — (Bundle version string, short)*
 * *Key* <br> CFBundleShortVersionString
 * *Human Readable Key* <br> Bundle version string, short
 * *Type* <br>String
 * *Optional*

#####Description
The version number of your stack.  
This should be a string in the standard version format, "1.2.3".  When a version number is available it will be displayed in the library detail view.
#####Available: Stacks API 2




