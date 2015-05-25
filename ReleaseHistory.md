# Introduction #

History of iUI releases.  For upcoming releases, see [Roadmap](Roadmap.md).

# Release 0.31 (October 5, 2009) #

  * Slide animation with CSS transitions is now on by default where enabled [Changeset](http://code.google.com/p/iui/source/detail?r=8d3d1894ca02dd9330fe1e176bd6727262fa9541)
  * Non-AJAX form submission when `target="_self"` ([Issue #136](https://code.google.com/p/iui/issues/detail?id=#136)) [Changeset](http://code.google.com/p/iui/source/detail?r=aa722436397a8300f3d903746255f1beca1df6f9)

# Release 0.30 (August 6, 2009) #

  * CSS Transitions for the 'slide effect'
    * [#26](http://code.google.com/p/iui/issues/detail?id=26) - Request to remove animation because it's slow
    * [#97](http://code.google.com/p/iui/issues/detail?id=97) - sliding too slow (Another smooth scroll patch using scrollTo is attached)
    * [#113](http://code.google.com/p/iui/issues/detail?id=113) - patch using webkit transition (didn't pass msgilligan's testing)
  * [ALL Issues currently slated to be Addressed in 0.30](http://code.google.com/p/iui/issues/list?can=1&q=milestone:REL-0.30&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary)

# Release 0.20 (May 8, 2009) #

Focus on fixing bugs.

  * First release with contributions to core of iUI from iPhoneWebDev members.
  * Use onorientationchange event for orientation with fallback to use of window.innerWidth.  ([Issue 84](http://code.google.com/p/iui/issues/detail?id=84))
  * Change value of `orient` attribute on `body` element for portrait mode from `profile` to `portrait`. ([Issue 85](http://code.google.com/p/iui/issues/detail?id=85))
  * [All Issues addressed in 0.20](http://code.google.com/p/iui/issues/list?q=label%3Amilestone%20label%3AREL-0.20&can=1)

# Previous Releases #

  * 2007-11-05: **Release 0.13**
    * Download: [iui-0.13.tar.gz](http://iui.googlecode.com/files/iui-0.13.tar.gz)
    * SVN tag: [REL-0.13](http://iui.googlecode.com/svn/tags/REL-0.13/)
    * Summary
      * Add Joe's examples directory to the SVN.
      * Add -webkit-box-sizing to CSS
      * Generate compressed CSS as part of Ant build
    * [Issues Addressed](http://code.google.com/p/iui/issues/list?can=1&q=milestone:REL-0.13&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary)
  * 2007-10-19: **Release 0.12** - First "Official" Google Code release
    * Download: [iui-0.12.tar.gz](http://iui.googlecode.com/files/iui-0.12.tar.gz)
    * SVN tag: [REL-0.12](http://iui.googlecode.com/svn/tags/REL-0.12/)
    * Summary
      * Formal release (on Google Code) of a tarball that matches Joe Hewitt's 0.12 zipfile release
      * Licensing clarified - we're using new BSD license.
      * Basic docs at iUI wiki http://code.google.com/p/iui/w/list
      * Number this version appropriately, and make sure there are appropriate links in code back to docs and source.
    * [Issues Addressed](http://code.google.com/p/iui/issues/list?can=1&q=milestone:REL-0.12&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary)
  * 2007-10-12: [initial-checkpoint](http://iui.googlecode.com/svn/tags/REL-initial-checkpoint/) tag - to checkpoint state before Sean and Christopher start work
  * 2007-07-17: Joe Hewitt's 0.12 release ([zipfile](http://www.joehewitt.com/iui/releases/iui-latest.zip) on his website)
  * 2007-07-16: Joe Hewitt's 0.11 release

## Experimental Branches in revision control system ##

  * [TRY-smooth-animation](http://iui.googlecode.com/hg?r=TRY-smooth-animation): (Joe's August 2007 changes for smoothscroll -- deemed not reliable enough for release -- see [#64](http://code.google.com/p/iui/issues/detail?id=64))

