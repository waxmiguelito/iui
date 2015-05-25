# Introduction #

In addition to iUI, Joe Hewitt,created something called [Firebug for iPhone](http://www.joehewitt.com/blog/firebug_for_iph.php)  It is less useful now that the iPhone has a developer mode that supports JavaScript logging, but may still be of value.

# Gotchas #

It seems to work with iPhone 1.1.4 with the following gotchas:

  * To avoid XSS limitations, the iBug server must be running on the same domain and port as the page you are debugging.  This means your page must be served by the Python HTTP server embedded in iBug.
  * You may need to increase the timeout on line 452 of ibug.js from 0 to 200, as follows:
```
    setTimeout(init, 200);
```
  * It doesn't work in the Aspen Simulator with iPhone software version 1.2 preview.

# Ruby Solution #

Nicholas Schlueter had to port it to Ruby to get around XSS issues while debugging Rails apps.  (The port is part of his  [iphone4r](http://svn.simpltry.com/plugins/iphone4r/) Rails plug-in)