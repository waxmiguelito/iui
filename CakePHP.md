# This page is deprecated until someone can update these instructions #
The comments say they don't work.

# Introduction #

[CakePHP](http://www.cakephp.org) is a Rails-like framework for PHP.

# Installation Instructions #

Thanks to Shaun Gish for providing these instructions:

  1. Download the latest release of [CakePHP](http://www.cakephp.org)  and iUI
  1. Install CakePHP as normal
  1. Place `iui.js` into the `/app/webroot/js` folder of your Cake install
  1. Make a new folder in `/app/webroot/img` called `iui` - place all images from iUI in there
  1. Place `iui.css` into `/app/webroot/css` (modify all image paths in the css to point to `/img/iui/imagename.extl`)
  1. Copy `/cake/libs/views/layouts/default.ctp` to `/app/views/layouts/default.ctp`
  1. Add `$javascript->link('iui');` and modify the css line to `$html->css (array('cake.generic', 'iui');`  (or you can alternatively use `$scripts_for_layout` and call the js from a view)
  1. Copy `/cake/libs/controllers/app_controller.php` to `/app/app_controller.php (notice the different path` - it's a Cake best practice)
  1. Add `var $helpers = array('Html', 'Javascript', 'Form');`  (you need the Html and Javascript helpers to use them and I always use the form helper so you may as well add it here)
  1. Open `/app/views/layouts/default.ctp` and remove everything in between the body tags except for `<?php echo $content_for_layout; ?>` (i suspect the problem that you were having is that the div id's that cake starts out with were conflicting with what iui displays by default.)

Seems like quite a bit of work but most of this is all standard CakePHP stuff when you first start out a project - I actually keep a project that I use as a base template setup this way - One of the things that I do is use a different layout for anything using iUI -  that way I can keep all of my logic in my controllers and just do a
simple check to see if the client is an iPhone or not and display the view with `iui.js` and `iui.css` loaded... have to tinker a bit to make everything work perfectly but it's not too bad.