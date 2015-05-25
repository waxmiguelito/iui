# Introduction #

iUI now has a website at [www.iui-js.org](http://www.iui-js.org) (in addition to this Google code site)  Work on the website is being discussed on the iui-developers Google Group.  (Thanks!)  If you'd like to get involved join us there.

# Thanks to CloudBees #

[![](http://www.cloudbees.com/sites/default/files/Button-Powered-by-CB.png)](http://www.cloudbees.com)

Thanks to CloudBees for providing us with hosting for http://www.iui-js.org and also for hosting our [Continuous Integration Server](ContinuousIntegration.md).

# Issues and To Do's #

We are now tracking website Issues in the Google Code Issues database.  If you search with the label `Component-Website`, you can see a [list of open issues](http://code.google.com/p/iui/issues/list?q=label:Component-Website).

Front end:
  * migrate some wiki pages into the current template?
  * add links to wiki pages?

Back end:
  * gallery splash page
  * gallery uploading
  * search engine (or just stick with the Google Search box?

# Web Site Source Code #

The source code for the site is in the ['iui.site' repository](https://github.com/iui/iui.site)  on GitHub.

# Editing the GSP Templates #

The iUI website is mostly static HTML, but it is currently using [Grails 2.0](http://grails.org/) and [GSP Templates](http://grails.org/doc/latest/guide/theWebLayer.html#gsp) to render the common elements (headers, footers, navigation) of the various pages.  (The documentation pages are still in straight HTML.)

## Layout Template ##

The layout template is in [grails-app/layouts/main.gsp](http://code.google.com/p/iui/source/browse/grails-app/views/layouts/main.gsp?repo=site).  The `<g:layoutBody />` tag is replaced with the body content from the other templates when a page is displayed.

## The 'g:link' tag and '$resource' ##

The only non-HTML tag you need to learn to edit the GSP templates is the [g:link tag](http://grails.org/doc/latest/ref/Tags/link.html).  The iUI site always uses this tag with the `mapping` attribute like this:
```
<g:link mapping="download">DOWNLOAD</g:link>
```

The `mapping` attribute will generate a link using a _named mapping_.  Named mappings allow us to move a page to a new URL, and have all the links that use that named mapping be automatically updated.  The named mappings (e.g. 'home', 'about', 'demo', etc.) are configured in [UrlMappings.groovy](http://code.google.com/p/iui/source/browse/grails-app/conf/UrlMappings.groovy?repo=site)

Links to static HTML pages in the documentation directory should use the [`$resource` method](http://grails.org/doc/latest/ref/Tags/resource.html) as follows:

```
<a href="${resource(dir: 'documentation/latest', file: 'getting-started.html')}">Getting Started</a>
```

The `$resource` method will correctly build the URL to a static resource based upon its internal path even if the server configuration is changed.

# Installing Grails and Running Locally #

It is highly recommended that you test your changes before doing a Git commit.  [Installing Grails](http://grails.org/doc/latest/guide/gettingStarted.html#downloadingAndInstalling) is easy if you're comfortable with basic command-line usage of Mac, Linux, or Windows.  On Mac OS X, I do it as follows:

  1. Download `grails-2.0.3.zip`
  1. Unzip in `/usr/local` (you should have a directory named `/usr/local/grails-2.0.3`)
  1. Create a symbolic link named `grails`:
```
 # ln -s grails-2.0.3 grails
```
  1. Create a symbolic link for the grails command in /usr/local/bin:
```
 # cd /usr/local/bin
 # ln -s grails ../grails/bin/grails
```
  1. Add the environment variable `GRAILS_HOME` to your `.bashrc`
```
export GRAILS_HOME=/usr/local/grails
```

In the future you can update to new versions of Grails by unzippig the new version in /usr/local and deleting and recreating the `grails` symbolic link.

To run the iUI WebSite in your local copy of Grails:
```
# cd iui.site
# grails run-app
```

You can now view the site at http://localhost:8080