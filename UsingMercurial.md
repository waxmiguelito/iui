# iUI has now switched to Git #

**iUI has switched to the Git revision control system, this page is deprecated**

Some of this information might be useful for accessing the old Mercurial repository that is still available for read-only access.

# Introduction #


iUI recently switched to the [Mercurial](http://www.selenic.com/mercurial/) Distributed Version Control System (DVCS).  Mercurial should make it easier for advanced users of iUI to track changes in the iUI source and to submit patches.  It should also make it easier for the iUI developers to evaluate and integrate patches, helping us to improve iUI more quickly.

## Advantages of Mercurial for non-committers ##
  * Easier for non-committers to use revision control on their own work
  * Easier to submit patches
  * Easier to [re-apply local patches](http://hgbook.red-bean.com/read/managing-change-with-mercurial-queues.html) after version update

## Advantages of Mercurial for committers ##
  * Easier to review patches
  * Easier to apply patches
  * Easier to create experimental branches
  * Higher performance for most operations

## Disadvantages of Mercurial ##
  * Have to learn new tool (but command-line is [very similar](http://hgbook.red-bean.com/read/migrating-to-mercurial.html#id442397) to SVN and [free, on-line guide](http://hgbook.red-bean.com/read/) is short and well-written)
  * Integrated with fewer tools (but this is changing quickly)

# Quick Links #
  * [Browse the iUI Mercurial Repository](http://code.google.com/p/iui/source/browse/)
  * [Information for repository checkout](http://code.google.com/p/iui/source/checkout)
  * [Clones of iUI](http://code.google.com/p/iui/source/clones) on Google Code

# About Mercurial #

[Distributed Version Control Systems](http://en.wikipedia.org/wiki/Revision_control#Distributed_revision_control) (DVCS) allow each user to have a complete copy of the repository and to create local, uniquely identified branches.  Patches or change-sets are easily transferred between repositories.  A particular repository may be declared the 'central' repository, but this is done purely by convention.

[Git](http://www.git-scm.org/) is probably the best known DVCS, and the feature set of Mercurial is very similar.  [Google chose Mercurial over Git](http://code.google.com/p/support/wiki/DVCSAnalysis) and now provides Google Code projects with a choice between Mercurial and Subversion.  The advantages of the DVCS approach had led some iUI developers to experiment with Git on [github](http://github.com), but now that Mercurial is integrated with Google Code we decided to abandon that effort.

Google Code supports [server-side cloning](http://googlecode.blogspot.com/2009/10/mercurial-server-side-clone-support-for.html) that will work for users of Google Code who are not iUI  committers.  See 'Create your own clone' on the [Clones of iUI](http://code.google.com/p/iui/source/clones) page.

### Mercurial Reference ###
  * [Home Page](http://www.selenic.com/mercurial/)
  * [Quick Start](http://mercurial.selenic.com/wiki/QuickStart)
  * [Mercurial: The Definitive Guide](http://hgbook.red-bean.com/read/) (Free on-line book, also available for purchase)

### Mercurial on Google Code ###
  * [Mercurial FAQ](http://code.google.com/p/support/wiki/MercurialFAQ)
  * [Preview Release Announcement](http://google-code-updates.blogspot.com/2009/04/mercurial-support-for-project-hosting.html)
  * [Availability to all projects announcement](http://google-code-updates.blogspot.com/2009/05/mercurial-now-available-to-all-open.html)
  * [Google Code blog: Server-side clone support](http://googlecode.blogspot.com/2009/10/mercurial-server-side-clone-support-for.html)

# Installing on Mac OS X #

Instructions:
  * Download package from http://mercurial.berkwood.com/  (tested with version 1.3)
  * Install using package installer

### Mac OS X Configuration ###

If you are using Mac OS X, add the following lines to your `.hgrc` file

```
[merge-tools]
filemerge.executable = /full/path/to/opendiff-w
filemerge.args = $local $other -ancestor $base -merge $output

[extensions]
extdiff=

[extdiff]
cmd.opendiff = opendiff-w
cmd.bbdiff = bbdiff
opts.bbdiff = --wait --resume
```

You'll also need to create the `opendiff-w` script file somewhere in your PATH:
```
# opendiff returns immediately, without waiting for FileMerge to exit.
# Piping the output makes opendiff wait for FileMerge.
opendiff "$@" | cat
```

  * `hg merge` should now use `FileMerge` through the `opendiff` command
  * `hg opendiff` should now do a diff with `opendiff`
  * `hg bbdiff` should use `bbdiff` if you have BBEdit and its command line tools installed

See: http://mercurial.selenic.com/wiki/ExtdiffExtension and http://mercurial.selenic.com/wiki/MergeProgram for details.

### Mac OS X GUI ###
  * [Murky](http://bitbucket.org/snej/murky/wiki/Home) - Cocoa App, BSD License
  * [Mac Mercurial](http://jwwalker.com/pages/macmerc.html) - Free, as in beer

# Upgrade Repo from SVN to Hg on OS X #

Reference:
  * [Converting Mercurial to Subversion](http://code.google.com/p/support/wiki/ConvertingSvnToHg)
  * [Mercurial Convert Extension](http://mercurial.selenic.com/wiki/ConvertExtension)

Steps:
  * Install Hg on OS X
  * Install Subversion 1.6.3 using package from Collabnet
  * Enable convert extension:
```
[extensions]
hgext.convert=
```
  * Run `hg convert http://iui.googlecode.com/svn/`
    * I don't understand how hg picks up the bindings to Subversion 1.6.3 since built-in 1.4 is not supposed to work
  * Push to Google Code