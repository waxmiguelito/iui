# Join iPhoneWebDev: Ask & Answer Questions, Solve Problems #
The support forum for iUI is [iPhoneWebDev](http://groups.google.com/group/iphonewebdev) on Google Groups. A great way to help out, be part of a community, and demonstrate your knowledge of iUI is to answer questions and help solve problems.

We are no genius and nobody can be always right, so if you think your answer can help, don't be shy if you are not 100% sure. Your contribution might lead to the final solution.

# Report Bugs #
Please submit bugs by using Google Code [Issues](http://code.google.com/p/iui/issues/list). Follow these simple steps:

  1. Note your iUI Version and any modifications you have made
  1. Search existing issues
  1. Enter the bug or add comment to existing bug as appropriate (a Google Code account might be needed)
  1. Wait for fix and test when available

# Provide a Reduced Test Case #
Create the simplest possible iUI page that reproduces any problem you are experiencing.  See the [WebKit Reduction Page](http://webkit.org/quality/reduction.html) for some useful tips. If you can't reproduce this bug with the simpliest iUI screen (demo screens for example), there is good a chance your modifications did create it (in this case, the [iPhoneWebDev](http://groups.google.com/group/iphonewebdev) support forum is there for you).

# Join the Developer Group #
Join the [iui-developers](http://groups.google.com/group/iui-developers) Google Group if you would like to contribute to the future of iUI or if you just want to keep up on the latest development.

There are also Google Groups for receiving automatic notifications of source control changes  ([iui-svn](http://groups.google.com/group/iui-svn)) and issue tracker changes ([iui-issues](http://groups.google.com/group/iui-issues))

# Discuss Your Patch on the List #
If possible discuss your patch **before starting work** -- this will help avoid duplicate effort and, if you're willing to take suggestions from the list, greatly increase the chances of your patch being accepted.

["How to get your code into an open source project"](http://et.redhat.com/~rjones/how-to-supply-code-to-open-source-projects) offers some great advice on how to produce the best patches and increase your chances of having them accepted.

# Submit Patches #
If you have a new feature, bug fix, or other improvement that you wish to contribute to iUI, please attach it to an _Issue_ in the [Issue Tracker](http://code.google.com/p/iui/issues/list).  A few guidelines to make things easier for everyone:
  1. Please check if the patch is a solution for an existing issue before creating a new one.
  1. If you have made many changes, please create a _separate issue for each change_.  To each issue attach a patch containing just that feature.  A big monolithic patch for many features has a much smaller chance of being accepted than several small patches that each fix a bug or add a useful feature.

# Preferred Patch Submission Method -- Git on GitHub #

  1. View our repository on [GitHub](https://github.com/iui/iUI)
  1. Click the "Fork" button
  1. Create a local clone of your fork
  1. If your change is anything more than a small patch, please make your change on a branch.
  1. Push changes from your local clone back to your forked repository.
  1. Create an Issue in Google Code Issues database explaining what bug is fixed or feature added.
  1. Submit a GitHub pull request


# Alternate Patch Submission Method -- Git on Google Code #

Google Code [supports Git](http://googlecode.blogspot.com/2011/08/announcing-git-support-for-google-code.html) and we have recently converted iUI's Google Code setup to use Git. To submit a patch with Git:

  1. Using your Web Browser, [Create a server-side clone](http://code.google.com/p/iui/source/createClone) of the iui repository. Please give it a name and description everybody can understand like _yourgoogleid_-iui-`purpose` (ex: msgilligan-iui-angularjs, remigrumeau-site-updates or erikbryn-iosdevcamp)
  1. Go to Administer -> Source in your clone repository and make sure "Enable Code Reviews" and "Allow non-members to review code" are both checked. This enables us all to +1 or -1 your submission(s), and decide in an open debate if we integrate it (or not) in the main iUI trunk.
  1. Go to Source -> Checkout in your clone repository for information on how to use `git clone` to make a copy of your clone repo on your computer.  (a local copy of your clone). This can be done with the git command line, or if your prefer with [a Git GUI client](http://git-scm.com/download) for your platform.
  1. Create a branch for your work. Name it something like _yourgoogleid_`-issue`_number_ or _yourgoogleid_-_patchdescription_ (ex: msgilligan-angularjs-tests or remigrumeau-site-updates-demo-video)
  1. Commit your changes to your local repository. On Git GUI, it's commonly in a "stage" panel. Please use the most comprehensive description possible.
  1. Push your changes to your server-side clone on Google Code. If asked, use "Origin".

Congrats!! Your changes might now be on Google Code. Now:

  1. Go to [Google code iUI clones page](http://code.google.com/p/iui/source/clones), choose your clone and go in Source / Changes. Your commit should be here. If you can't see it, check out "Branch".
  1. Once found, put the URL to your server-side changeset in a comment on the appropriate issue on Google Code.
  1. Send an e-mail to iui-developers telling us the changeset is ready.

# Alternative Method: Attach a file to the Issues Database #

  1. Use the "Attach a file" feature to attach a standard (diff-format) patch file or attach an entire file or group of files.
  1. Send an e-mail to iui-developers telling us the patch is ready.

# Additional Guidelines #
We should try to develop this section, similar to the [Webkit Code Contribution](http://webkit.org/coding/contributing.html) guidelines.