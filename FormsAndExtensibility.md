# Introduction #

The focus of iUI 0.40 will be forms and extensibility.  Many users have been requesting a mechanism that makes it easier to extend iUI -- many of the requests are related to solving issues with the use of HTML forms.  This wiki document will serve as a proposal/specification for that work.

# Goals #

## Forms ##
  * To be able to handle all major use cases for HTML forms and Ajax Post/Get requests
  * Improved documentation/samples on Forms (may happen after 0.40 release, but is important)
  * Advanced forms can use extensibility mechanisms

## Extensibility ##
  * Keep the iUI core small, but have a flexible extension mechanism
  * Use existing patches as test cases to see if they can use extension mechanism and not require mods to iui.js
  * Provide four categories of plugins
    * "Core" plugins -- included in the iUI distribution and included in prebuilt versions of iui.js
    * "Optional" plugins -- included  in  the iUI distribution but explicitly included  in webapps that use themm
    * "Sandbox" plugins will be in the iUI Mercurial Repository and maybe even documented on the wiki, but won't be part of the default distribution.
    * "3rd Party" plugins will be developed by the community and hosted elsewhere (but we can have a wiki page that references them)


# Existing Work #

### Patches ###
  * [Issue #102](https://code.google.com/p/iui/issues/detail?id=#102) - loading scripts (Wayne Pan)
  * [Issue #113](https://code.google.com/p/iui/issues/detail?id=#113) - Multiple enhancements (astrewt)
  * [Issue #127](https://code.google.com/p/iui/issues/detail?id=#127) - Dynamically load stylesheet (C.W. Zachary)
  * [Issue #128](https://code.google.com/p/iui/issues/detail?id=#128) -  Dynamically load script (C.W. Zachary)
  * [Issue #129](https://code.google.com/p/iui/issues/detail?id=#129) -  OnLoad event for panel (C.W. Zachary)
  * [Issue #130](https://code.google.com/p/iui/issues/detail?id=#130) -  OnFocus event for panel (C.W. Zachary)
  * [Issue #131](https://code.google.com/p/iui/issues/detail?id=#131) - OnBlur event for panel (C.W. Zachary)
  * [Issue #132](https://code.google.com/p/iui/issues/detail?id=#132) - OnUnload event for panel (C.W. Zachary)
  * [Issue #133](https://code.google.com/p/iui/issues/detail?id=#133) - Alter action button in toobar (C.W. Zachary)
  * [Issue #153](https://code.google.com/p/iui/issues/detail?id=#153) - multiple enhancements (Speednet)
  * [Issue #161](https://code.google.com/p/iui/issues/detail?id=#161) - patches for form GET

# Requirements #

### Issues (Forms) ###
  * [Issue #8](https://code.google.com/p/iui/issues/detail?id=#8) - Need visual feedback while loading form submission
  * Need form debouncing to prevent multiple submits (is there an issue for this?)

### Reported Issues (Extensibility) ###
  * [Issue #24](https://code.google.com/p/iui/issues/detail?id=#24)  - Callbackfor preprocessing data BEFORE inserting into the DOM

## Form Requirements ##
  * Submit Ajax forms with GET and POST
  * Submit forms via programmatic JavaScript
  * Submit non-ajax form (to load new page)
  * Form validation/post-processing before sending
  * Data modification on return before DOM insert
  * Form submission user feedback (spinner?)
  * User interface issues - should a form result slide in from the right?  etc.

## Plugin Requirements ##
  * Process loaded fragment before DOM insertion
  * Process page/fragment before making selected (onFocus)
    * before and/or after slide effect  (?)
  * Processing after page/fragment is unselected (onBlur)
  * Processing after unloading (backward nav (onUnload)
  * Easy modification of form object before submission
  * Use of XHR code that already exists in iui

TBD

# Design Proposal #

**Note: an implementation of this proposal is in the 0.40-dev2 release of iUI**

Use synthetic events to implement the 'observer' pattern and allow plug-ins to be called when key events occur in the core `iui.js` code.  The following events should implement all use cases.  (If you know of a use case that's not covered post a comment to this page or join us on iui-developers.)

## Events ##
  * beforeInsert (view) - called once for each loaded fragment
  * afterInsert (view) - called once for each child of the fragment that is inserted
  * afterInsertEnd - called once for each fragment after all children are inserted
  * load (view)
  * unload (view)
  * onFocus (view)
  * onBlur (view)
  * beforeTransition
  * afterTransition


# Packaging/Bundling Systems #
  * [Jawr](http://jawr.dev.java.net/)
  * [Dojo](http://www.dojotoolkit.org/book/dojo-book-0-9/part-4-meta-dojo/package-system-and-custom-builds)