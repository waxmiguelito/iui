# Introduction #

iUI now has a [Continuous Integration](http://martinfowler.com/articles/continuousIntegration.html) (CI) server that will make up-to-date test releases of the latest version of iUI from the 'master' branch of the main iUI repository.  CI servers are also known as build servers.  The [iUI CI server](https://iui.ci.cloudbees.com/job/iUI/) will generate a new build of iUI whenever any change is checked in to the main iUI repository.

# Downloading CI Builds: Caveat Emptor #

Anyone may download a CI build, but should be aware that there are **no guarantees** as to how well these releases will work.  To look at recent builds visit the [CI server dashboard](https://iui.ci.cloudbees.com/job/iUI/) and pick a recent build that appears to be successful.

Most users should download stable builds of iUI from the Google Code [download page](http://code.google.com/p/iui/downloads/list).  Only use a build from the CI server if you are experienced with iUI and are willing and able to keep track of the latest changes being made by the iUI core developers.  (If you wish to be involved at this level, please join the [groups.google.com/group/iui-developers iui-developers Group]).

# Bookmarks #
  * [iUI CI Homepage](https://iui.ci.cloudbees.com/job/iUI/)
  * [CI Changelog](https://iui.ci.cloudbees.com/job/iUI/changes)
  * [Last Successful Build](https://iui.ci.cloudbees.com/job/iUI/lastSuccessfulBuild/)
  * [Console Output of last successful build](https://iui.ci.cloudbees.com/job/iUI/lastSuccessfulBuild/console)

# Details #

The iUI CI server is using a CloudBees-hosted version of the [Jenkins CI](http://jenkins-ci.org/) server.  **Whenever anything new is pushed to the main iUI repository  the CI server will build a new release of iUI**.  (Even a 1-word change in a documentation file will result in a new build.)

Each build is assigned a sequential number that uniquely identifies that build.  The build number and build date & time are placed in the version timestamp in the iui.js and iui.css files and is also used in the filename for the downloadable zip file.

CI downloads have filenames that look like this:

```
iui-build-<buildNum>_<date>_<time>.zip
```
for example:
```
iui-build-12_2012-04-28_15-34-47.zip
```

The CI server builds iUI zipfiles using the following [Ant](http://ant.apache.org/) command:
```
ant iui-clean iui-zipfile
```
For details on how iUI is built, see ReleaseProcess.

(Note that our CI server is actually pulling updates from a GitHub mirror of the iUI repository.)

# Thanks to Our Sponsor: CloudBees #

[![](http://www.cloudbees.com/sites/default/files/Button-Built-on-CB-1.png)](http://www.cloudbees.com/)

The CI server is generously powered by the [DEV@Cloud](http://www.cloudbees.com/dev.cb) service of [CloudBees](http://www.cloudbees.com/) through their [FOSS support program.](http://www.cloudbees.com/foss/foss-dev.cb)  Thanks, CloudBees!  (As soon as we get a few more details sorted out, we'll put your badge on our main website and tweet about you, etc.)