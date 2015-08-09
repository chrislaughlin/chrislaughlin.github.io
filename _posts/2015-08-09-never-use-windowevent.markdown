---
layout: post
title: "Never use Window.event"
date: "2015-08-09"
---
I had recently fixed bugs in different applications each with the same mistake.
In both instances the developer had used the ```Window.event``` object inside a browser
event. Something like below:

``` javascript
buttonClicked: function() {
  if(Window.event.currentTarget) {
    .....
  }
}
```

The main issue here is we are using the browser created global event object, this is
specific to IE and chrome. So what is bad about that you ask? Firefox does *not* support
this and your application has now lost all Firefox support. The proper way to handle
the events is to use the event param that is passed to the function by default.

``` javascript
buttonClicked: function(event) {
  if(event.currentTarget) {
    .....
  }
}
```
This method is supported by all browsers. This method also moves you away from
using the Window object which is a global and out of priceable should be avoided
when possible.
