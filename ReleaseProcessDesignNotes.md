# Issues #
  * .tar.gz only (we may add .zip later if there is demand)?
  * Installation process: just extract into webapp directory.  (At least for now)
  * Javascript compression/packing, dead-code elimination, etc (Not in initial releases)
  * Standalone vs. prototype/scriptaculous version?
    * Are there really going to be two versions going forward?
      * We are planning on eliminating the prototype version shortly, unless someone volunteers to support it
    * How to apply DRY principle if there are two version
  * How to keep versions in sync with SVN, release notes, bug db, etc.
  * What OS and/or tools are required for release process?
    * Mac OS X 10.4 and bash shell are used for "official" releases.
    * Java 5.0, Groovy, and Gant

# Possible Tools/Languages #
  * Shell Script
  * Makefile
  * JavaScript/[Rhino](http://www.mozilla.org/rhino/)
  * [Ruby](http://www.ruby-lang.org)/[Rake](http://rake.rubyforge.org/)
  * Java/[Ant](http://ant.apache.org/)
    * Used by Dojo build (optimization) process
    * Google Code has Ant support for scripted uploads to the download page
  * [Groovy](http://groovy.codehaus.org/)/[Gant](http://groovy.codehaus.org/Gant)
    * Groovy is a Ruby-like scripting language on the Java platform
    * Gant allows you to script Ant tasks without XML :)
  * Python
    * Google Code has Python support for scripted uploads to the download page
  * [ShrinkSafe](http://dojotoolkit.org/docs/shrinksafe)
  * Are there any relevant Google Code tools?
    * [Scripted Uploads](http://code.google.com/p/support/wiki/ScriptedUploads)

# Proposed Tools/Language #
  * Java/[Ant](http://ant.apache.org/)
    * Shrink Safe
      * [compress-js](http://www.lcasoft.com/compress-js.html) Ant task from lcasoft.com
      * custom\_rhino.jar from lcasoft.com (latest version from Dojo site is not compatible with Ant task)
    * [ant-googlecode](http://code.google.com/p/ant-googlecode/) Ant task for upload to Google code (not tested, requires Ant 1.7)
    * [YUI Compressor](http://developer.yahoo.com/yui/compressor/)