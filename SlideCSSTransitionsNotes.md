# Introduction #

iUI 0.30 and later has support for hardware-assisted slide transitions using WebKit CSS Transitions.  However, in release 0.30, this support is disabled by default.  In release 0.31 and later, it is enabled by default.

# Warning #

CSS Transitions will only work correctly if your CSS is done exactly right.  Applications that wish to use CSS Slide Transitions must have their CSS carefully reviewed by someone who is knowledgeable about WebKit Transitions  and the CSS required to implement them correctly.  Although CSS Slide Transitions work in all the iUI samples and are working in a number of 3rd-party applications, using iUI does not guarantee that CSS Slide Transitions will work correctly in your application.  If you are having trouble with WebKit CSS Transitions, you may want to disable the `iui.animOn` flag as described below.

# Enabling #

To enable CSS Slide Transitions in your iUI application you'll need to make sure the `animOn` flag in iUI.  In release 0.31 and later it is on by default, but you might want to make sure that you haven't disabled it.

In version 0.30, you had to do this with one line of JavaScript in the `<head>` of your HTML page as shown below:
```
<script type="text/javascript">
	iui.animOn = true;
</script>
```


If you are running version 0.31 or later, you can disable CSS transitions by adding the following to the `<head>` of your HTML page:
```
<script type="text/javascript">
	iui.animOn = false;
</script>
```

**Note: when CSS transitions are disabled, iUI falls back to using a JavaScript timer to do the transitions**

# Debugging #

If you are having trouble getting CSS Slide Transitions to work with your iUI-based application, here is a list of things to try:

  1. Disable CSS transitions as shown above to make sure that your problem is related to CSS transitions.
  1. Set the `-webkit-transition-duration` to `3000ms` so you can watch the transition in slow-motion.  Common problems with CSS Slide Transitions are that the outgoing block and/or the incoming block does not animate the change to the `-webkit-transform: translateX` property but the change takes place immediately.  By closely watching the slow-motion transition you may be able to whether the problem affects the incoming block, the outgoing block or both.  You may also find setting an opacity property on one or both of the blocks may help  you visualize what is happening.
  1. Make sure that the incoming block does not have the `selected="true"` attribute set.  `iui.js` will set this attribute automatically at the correct time.
  1. Carefully compare any changes/additions you have made to either the CSS or the JavaScript  with the working iUI Sample applications.  Temporarily disable any changes you have made to see if there is any difference in behavior.