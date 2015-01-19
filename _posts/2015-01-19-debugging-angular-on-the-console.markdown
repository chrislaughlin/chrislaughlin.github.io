---
layout: post
title: "Debugging Angular on the Console"
date: "2015-01-19"
---
## Debugging Angular on the Console

I was recently working on a defect on a large AngularJS project at work and needed
to get access to an asset (product) in the JavaScript console. My normal path for
this is to drop a breakpoint in a controller and the use the console. However I
was already on a breakpoint and the service I was in need of, did not get
injected into the service. So after some searching I found the following snippet
and it worked a charm. Not only does this work when you are stopped anywhere in
the application but it also works when your not stopped.

{% highlight javascript %}
angular.element(document.querySelector('html')).injector().get('Service/factory Name');
{% endhighlight %}  

The above works for any service just repalce 'Service/factory Name' with what you need.
you can test this out on the [todo MVC Angular app](http://todomvc.com/examples/angularjs_require/#/)
run the following from the console after you have added at least one todo:

{% highlight javascript %}
angular.element(document.querySelector('html')).injector().get('todoStorage').get()
{% endhighlight %}  
