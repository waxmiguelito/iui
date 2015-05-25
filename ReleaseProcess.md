# Summary #

iUI has a release process that is used by the iUI project team to assemble and release images (zip files) and push them to the Google Code download site.

You do not need to read this document to use iUI.  If you are curious about how iUI is managed by the iUI Project Team, you may find this document of some value.

# Setup Procedure #
  * Make sure you have Java 6.0  (aka 1.6) or later installed on your system.
  * Make sure you have [Apache Ant](http://ant.apache.org/) 1.7.0 or later installed on your system.
  * Make sure the `ant` command on the command line will run the correct version of ant
    * ` # which ant `
    * ` # ant -version `

## Official Build with Mac OS X 10.6 ##
  * Mac OS X 10.6.6
  * Java Version 1.6.0\_26
  * Ant 1.7.0 installed in /usr/local/bin/ant (Developer Tools now has 1.8.2 - we should try it)

# Release Process (used for 0.4 release) #
  * Make sure the version number is set in a comment in `build.properties` :
    * Set `iui.version` and `iui.release.summary` in comment in build.properties
  * Update release notes in ` releaseNotes.txt `
  * Commit to GitHub
  * Start in a freshly checked out or exported directory.
    * ` git clone git@github.com:iui/iUI.git iui-release-dir-xx `
    * (This step is important as it prevents accidental release of intermediate files, etc)
    * (We should probably include instructions to checkout and build a specific revision, like we had for Hg)
  * Make sure your current working shell directory is the iui project root
    * (The directory that contains `build.xml`)
  * Make sure the version number is set:
    * ` # cp build.properties local.build.properties `
    * Edit `local.build.properties` to have your Google Code username/password
    * Make sure the `iui.version` and `iui.release.summary` are set correctly in `local.build.properties`
  * To get list of ant tasks: ` # ant -p `
  * To make a release zipfile: ` # ant iui-zipfile `
    * In earlier releases tar.gz format was used:  ` # ant iui-tarball `
  * To upload a release to Google code:
    * Make sure version number is set and release notes are written (see above)
    * ` # ant iui-release `
    * Tag with Git (**Note: We should probably start using annotated tags for REL-_version_** -- but not REL-current)
      * `# git tag -a REL-`_version_` -m "`_message_`"`
    * Update the `REL-current` tag to reference the latest stable release
      * `# git tag --force REL-current `
    * Push changes and new tags to 'origin' repo on GitHub
      * `# git push --tags origin master`
    * Using Google Code Web UI, mark the new release as `deprecated` to hide it from casual users.
    * Announce on iui-developers list to get feedback (+1's) from other developers before announcing.

# Things to release besides the zipfile #
  * Update the [demo site](http://demo.iui-js.org) on GAE.
  * Update the documentation on the [iUI Website](http://www.iui-js.org) to match the release version
    * Update the iUI Git submodule
      * `# cd iui.site/web-app/documentation/latest/iui`
      * `# git pull `
      * `# cd iui.site`
      * `# git add web-app/documentation/latest/iui`
      * `# git ci -m "updated iui submodule to new version"`
  * Update the [Download page](http://www.iui-js.org/download) on the [website](http://www.iui-js.org).

# Announcement Process #
  * Remove `deprecated` tag on Google Code download page.  If the release is designated 'stable' add the `featured` tag.
  * The `featured` tag on the download will update the iUI Google Code home page
  * Announce on iui-developers
  * Announce on iPhoneWebDev
  * Announce on Twitter using `#iuijs` hashtag
  * Announce on the Facebook page
  * Announce on personal blogs, etc.
