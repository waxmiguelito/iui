# Introduction #

Many users of iUI have customized the CSS and images to create a custom look for their iPhone site or application.   iUI version 0.40 (and later) will have explicit support for themes.  This Wiki page describes best practices for creating a custom iUI theme.

# Details #

  1. iUI themes are distinguished by a ThemeID.  A ThemeID is a short string, of usually lowercase characters, such as `ipdc`
  1. A theme is stored in a directory whose name is the ThemeID.  In the iUI distribution theme directories are children of the `iui/t` directory.  For example the `ipdc` theme lives in `iui/t/ipdc`.
  1. A theme has a _themeid_`-theme.css` file containing the CSS customizations for the theme.
  1. The theme CSS file and all associated images are placed in the theme directory.


Note: The original/default theme is not currently packaged using theme guidelines, but may be in the future.
Note: Themes do not currently include any custom JavaScript.  Although you are always free to write some for your site.

# Example #

At iPhoneDevCamp 3, we are creating an iUI theme with the iPhoneDevCamp logo and colors.  More info will be here shortly.

| ThemeID | `ipdc` |
|:--------|:-------|
| Theme Directory | [iui/t/ipdc](http://iui.googlecode.com/hg/iui/t/ipdc/) |
| CSS Filename | [iui/t/ipdc/ipdc-theme.css](http://iui.googlecode.com/hg/iui/t/ipdc/ipdc-theme.css) |
| Images  | [image directory](http://iui.googlecode.com/hg/iui/t/ipdc/) |

# Theme Switcher #

There is currently an experimental theme switcher in the trunk of the Mercurial (Hg) repository.  It is a work in progress and (among other things) does not (yet) set a cookie to remember the theme across page reloads.  Still it is useful for theme comparison and development.  The theme switcher is available in a panel of the [Music Sample app](http://demo.iui-js.org/samples/music/music.html).


