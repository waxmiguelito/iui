# Introduction #

This is the roadmap.

**Disclaimer**: Please remember that the developers of iUI are volunteers and this roadmap is in no way a commitment that any of these proposed features will ever be completed.

# Release 0.4 (RELEASED August 11, 2012) #

**[Download](https://code.google.com/p/iui/downloads/list)**

**[Release Notes](https://github.com/iui/iUI/blob/master/releaseNotes.txt)**

**Note: iUI 0.4 has been released but we still need to close some issues in the Issues DB and update the below list**

Release 0.4 features and fixes not final, but a proposed list is here:

  * Support for custom [Themes](Themes.md) (aka "skins")
  * Clean up [form handling](FormsAndExtensibility.md) and documentation
  * [Extensibility](FormsAndExtensibility.md)
    * [#24](http://code.google.com/p/iui/issues/detail?id=24) - Hook to call add-ons when fragments are Ajax-loaded
    * This should enable some other interesting features as add-ons (script loading, etc)
  * Sandbox Extensions (i.e. pre-alpha or alpha)
    * [iScroll](http://cubiq.org/scrolling-div-for-mobile-webkit-turns-3) - Scrolling under NavBar and under a fixed Tab Bar, etc. ([iScroll Extension Wiki Page](iScrollExtension.md))
    * HTML 5 Cache Manager
    * Google Analytics
    * JavaScript loader - loads/runs JavaScript in views loaded via AJAX ("just in time")
    * TbBMod - modifies navbar buttons on the fly - and more!
    * Masabi - provides calendar control, sliding form-picker panels, etc.
  * Sandbox Themes
    * iPhoneDevCamp theme
    * Default theme using gradients
    * Android Theme
    * WebOS Theme
  * Some bug fixes previously slated for 0.30
  * High priority bug fixes
  * [OPEN Issues currently slated to be Addressed in 0.40](http://code.google.com/p/iui/issues/list?can=2&q=milestone:REL-0.40&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary)
  * [ALL Issues currently slated to be Addressed in 0.40](http://code.google.com/p/iui/issues/list?can=1&q=milestone:REL-0.40&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary)

# Release 0.4.1 (October 2012) #
  * Event Bubbling Fix, see the [Pull Request](https://github.com/iui/iUI/pull/6) and the developer's list [explanation](https://groups.google.com/forum/?fromgroups=#!topic/iui-developers/EgnHFv2Oqpw) and [discussion](https://groups.google.com/forum/?fromgroups=#!topic/iui-developers/NkYUBsVOuIE).

# Release 0.5 (Unstable release  - November 2012) #
  * Theme refactoring (Remi)
  * iScroll and iPad support
  * Directory restructuring
  * Code cleanup
  * LESS CSS support
  * Improved build system
  * Other (TBD)
  * [OPEN Issues currently slated to be Addressed in 0.5](http://code.google.com/p/iui/issues/list?can=2&q=milestone:REL-0.50&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary)
  * [ALL Issues currently slated to be Addressed in 0.5](http://code.google.com/p/iui/issues/list?can=1&q=milestone:REL-0.50&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary)

# Release 0.6 #
  * Stable release of features developed during 0.5

# Release 0.7 #
  * Anything not 100% essential for 0.6
  * Other (TBD)
  * [OPEN Issues currently slated to be Addressed in 0.6](http://code.google.com/p/iui/issues/list?can=2&q=milestone:REL-0.6&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary)
  * [ALL Issues currently slated to be Addressed in 0.6](http://code.google.com/p/iui/issues/list?can=1&q=milestone:REL-0.6&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary)

# Release 0.8 #
  * Stable release of 0.7 features

# Release 0.9 #
  * Working towards the "final" release 1.0

# Release 1.0 #
  * Final release of original iUI.

# Release 2.0 #
  * Other significant changes

# Future #

  * Clean up iUI architecture, expand functionality, better docs and examples.
    * More error handling
    * Better docs and samples, including some backend code in a variety of languages (anyone want to contribute?).
    * Investigate larger architecture issues, such as optional callbacks.
  * Demonstrate other kinds of iPhone user interfaces
    * Tabs (like in the iTunes Wi-Fi app)
    * Moving items up/down
    * Other
  * Make examples that work with AdMob and Google Mobile Adsense.
  * Investigate ability to turn off iPhone specific UI elements when run on non-iPhone webkit phones, yet still functional.
  * Take advantage of any new features offered by updates to Mobile Safari.
  * Microformat for identifying iPhone web apps.