# Introduction #

iUI 2.0 will add support for split-screen mode and other UI elements and behaviors that are modeled after the behavior of native applications on the iPad.  It is useful for producing websites for both iPhone-class mobile devices and iPad-class touchscreen tablets and also results in reasonable behavior on desktop/laptop browsers.

**Note: There will be a single version of iUI that can be used for touch sites for mobile, tablet, and/or desktop depending upon configuration**

# Features #

This is a preliminary list of features updated just after iPadDevCamp.  Please comment below or join the [iui-developers](http://groups.google.com/group/iui-developers) group if you would like to discuss in detail.

## Planned for First Release ##

  * Fixed header and footer (using iUI's prototype iScroll plugin)
  * Split-screen operation
    * Navigation in left pane
    * Content in right pane
  * Fallback to single-pane  operation on smaller screens (e.g. iPhone)
  * Popover
    * Navigation pane becomes a popover in portrait mode
    * By default popover mode  is activated only for Touch devices

## Future Releases ##

  * Multiple navigation stacks
    * Allows navigation stack/hierarchy to be used in left and right panes
    * Will allow multiple navigation stacks on apps with a tab-bar on the bottom

# User Experience #

Split screen navigation allows iUI applications to make better use of larger screens when they are present.  It also provides a familiar touch-based interface on the iPad or for desktop/laptop users who are familiar with the iPad.

## Modes of Operation ##

### Single Pane ###

This is how the current versions of iUI operate and will continue to be supported.

### Split Screen ###

In split screen mode, the navigation items (generally `<ul>` elements) are displayed in the left pane, but when the user touches a link to a content ("leaf") node (usually a `<div>` element) it is displayed in the right pane.

### Popover Mode ###

In popover mode the navigation pane is initially hidden.  (Popover mode is typically activated by rotating to portrait orientation.)  A button (with a title matching the current title of the current navigation view) appears on the left hand side of the top bar.  When this button is touched  the popover will be  displayed.  Touching anywhere outside of the popover will hide the popover until the button is touched again.

### Mode Matrix ###

The following matrix indicates which modes of operation should be active in a default configuration.

| Screen  Size | Has Touch | Orientation | Mode |
|:-------------|:----------|:------------|:-----|
| Width < 750  | -         | -           | Single Pane |
| Width > 750  | -         | Landscape   | Split Screen |
| Width > 750  | No        | Portrait    | Split Screen |
| Width > 750  | Yes       | Portrait    | Popover Mode |

We may adjust the width threshold to a different value based upon user and developer feedback.  Although iUI does support detection of portrait/landscape on desktop browsers, switching between Split Screen and Popover  mode based upon the window size seems like it would be confusing for end users.  The default behavior for selecting mode of operation can be overridden for a specific site or for testing/debugging with a desktop browser.

Note: the current test for screen size uses `window.innerWidth` but it shouldn't because we don't want desktop browsers switching between split-screen mode and single-pane mode as the user resizes the browser (but it is handy during testing)  We'll need to test for mobile/touch devices with a size of less than `splitScreenMinWidth` (750) rather than simply using `innerWidth`.

# Configuration of Split Screen Behavior #

## Single Pane Only ("Classic") ##

All existing iUI apps will operate unchanged when they upgrade to a version of `iui.js` that has split screen support.

In current released versions of iUI this means you have iUI views (aka pages or fragments) that are children of the `<body>` tag.  In upcoming versions of iUI we'll encourage putting the iUI views under an iUI `<div>` that will be marked with a unique ID and/or class.  (In the prototype we're looking for `div#iui-container` but that will probably change soon -- feedback?)

## Split Pane Support ##

Split pane support will be enabled with the proper markup.

In the prototype version, split screen support is enabled by the presence of the following markup under the body tag after the `div#iui-container`

```
  <div id="iuipad-content-panel">
    <div class="toolbar">
        <h1 id="contentTitle"></h1>
        <a class="button leftButton" href="javascript:popover_toc()" id="toc_button">TOC</a>
    </div>
    <div class="wrapper">
      <div class="scroller">
        <div id="iuipad-content">
        </div>
      </div>
    </div>
  </div>
```

When split-pane support is enabled the WebApp will behave (by default) as described in the "Mode Matrix" subsection of "User Experience" above.  On Touch-enabled devices portrait mode will result in the left (navigation) pane becoming a popover.  On non-touch devices the left pane will always be displayed.

On touch devices iUI load-time initialization will set `iui.splitScreenConfig = ssConfig.auto` and on non-touch devices it will set  `iui.splitScreenConfig = ssConfig.noPopover`  (Forcing `iui.splitScreenConfig = ssConfig.auto` on a non-touch device will allow testing/debugging of popover mode and forcing `iui.splitScreenConfig = ssConfig.disabled` will allow testing of single-pane (iPhone) mode.  For now you might have to hack `iui.js` to force those modes, but we will provide a defined hook shortly.)

# Design Details #

(THIS IS CURRENTLY OUT OF SYNC WITH THE CODE AND NEEDS TO BE UPDATED)

Nav stacks contained in popovers or split screens have the effect of flattening the nav hierarchy by one.  The nav stack and the "main" or linked content are shown on the screen at the same time.

**content-pane**
There can only be one div (or block) on the page which has this class.  In landscape mode, this div is displayed in the right hand side of the split screen; in portrait mode, it fills the viewport.

**selected=true**
The selected property is set to true for the div or UL that is the current navigation view.  In landscape it is displayed on the left hand screen split; in portrait it is shown in a popover.

To launch the nav popover, set a link href to the anchor tag of the nav UL or div that should be shown.

When the content div is reloaded, a wait graphic will be faded in and out.

# Project History #

This sub-project of iUI was started at [iPadDevCamp](iPadDevCamp2010.md).  It was entered in the [Hackathon](http://www.iphonedevcamp.org/2010/04/11/participating-in-the-hackathon/) where it [won the Best Web App](http://www.iphonedevcamp.org/2010/04/18/quick-list-of-hackathon-winners) category.

# Project Resources #

  * [Source Code](http://code.google.com/r/msgilligan-iuiscroll/source) is in the msgilligan-iuiscroll Mercurial Clone.
  * The in-progress demo apps are on Google App Engine (iUI staging area):
    * [ipad-demo.html](http://stage.iui-js.org/samples/iuipad/ipad-demo.html)
    * [html5reference.html](http://stage.iui-js.org/samples/iuipad/html5reference.html) (currently broken)
  * Estelle "Standardista' Weyl has [posted](http://twitter.com/estellevw/status/13332994544) the HTML 5 Reference demo to it's own [domain](http://html5.touchref.com/).