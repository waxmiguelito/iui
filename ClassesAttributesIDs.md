# Introduction #

iUI allows web developers to create iPhone-styled mobile sites simply by creating properly formatted static HTML.  "Properly Formatted" means that a certain basic structure must be followed.  In addition iUI uses specific values for `id` and `class` attributes to designate the styling and behavior of certain elements.


# IDs #

  * `#pageTitle`

# Classes #

  * `.toolbar`
  * `.panel`

# Target Values #

  * _no target_ Link is to a fragment that is either already loaded (in the case of an anchor in current doc) or to be loaded via AJAX (in the case of a link to another HTTP document)
  * `_self` Load `href` as new page replacing the current page
  * `_replace` Load `href` to replace the parent of the link element.
  * `_webapp` Similar to `_self` but, if running as a WebApp, open link in current WebApp rather than opening in Safari

# Extended Attributes #

  * orientation
  * selected
  * title

# Extended Attributes and (X)HTML Validation #

  * iUI uses xyz which means they can't be XHTML strict

Pete McConville has contributed a custom DTD that can be used for validating iUI documents:  See [Issue #149](https://code.google.com/p/iui/issues/detail?id=#149).
