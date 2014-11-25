---
title: 'NOOP: No Operation Function'
author: chris
layout: post
permalink: /2014/08/25/noop-no-operation-function/
dsq_thread_id:
  - 2957276391
categories:
  - javascript
tags:
  - angular
  - callback
  - function
  - javascript
  - jquery
  - noop
---
> *A function that performs no operations. This function can be useful when writing code in the functional style.*

The noop function seem pointless when you first look at it but, once you see it in action you realise that it provides a
method of keeping code clean and maintainable. One main example I have seen of the noop function is in the jQuery source
when defining a properties on an object and wanting to add an empty function as a placeholder:


&nbsp;



The noop function was introduced into jQuery in <a href="https://github.com/jquery/jquery/commit/6cb2945837ccca55204191a8e7a70b2b2486c28e"
target="_blank">December 2009</a> as a better way of using anonymous empty functions, it actually provides a small (1-10%) performance improvement a
s a new function reference is not created each time noop is used. The function has been added to other JavaScript libraries
 so provide support of this pattern these include <a href="https://docs.angularjs.org/api/ng/function/angular.noop" target="_blank">Angular</a>
  and as mention above <a href="http://api.jquery.com/jquery.noop/" target="_blank">jQuery</a>. There is also a pure JavaScript way off achieving
  this by using Function.prototype();

This does not provide a load of advantage but in my option can clean up code and can reduce some line number. It&#8217;s
a nifty little part of jQuery I had never seen before and though I would share.