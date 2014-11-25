---
title: 5 Most Depended-upon NPM Packages
author: chris
layout: post
permalink: /2014/07/15/5-most-depended-upon-npm-packages/
dsq_thread_id:
  - 2852114032
categories:
  - applications
  - development
  - javascript
tags:
  - javascript
  - npm
  - packages
---
So after my last post on npm packages being removed, I started to realise that I don&#8217;t know that many packages and most of the times I use what was already installed in the project. So I took to the interwebs looking for some most used packages. This led me to the list of the most <a href="https://www.npmjs.org/browse/depended" target="_blank">depended-upon</a> packages and here is a run down of the top 5:

&nbsp;

## <a title="Underscore package" href="https://www.npmjs.org/browse/depended/underscore" target="_blank">Underscore</a>

###### <span style="color: #666666;">6481 Packages</span>

Underscore is a until library that is not only used for NodeJs application but for any JavaScript application, it can be easily seen by the signature &#8220;\_.&#8221;  with methods that can manage a wide range of action from simple null and undefined checks to searching, filtering and mapping arrays. I use underscore currently with an Angular application to add more functionality to arrays.  The most popular methods include \_.each, \_.some and \_.uniq. Looping an array, searching an array and removing duplicates are all simple operations but do require some redundant code. Underscore provides a simple to use array of helper methods all working from closures. Although recent advancements in JavaScript performance has seen other libraries such as <a title="Lazy JS" href="http://danieltao.com/lazy.js/" target="_blank">Lazy JS</a> come out and claim to be faster than underscore.

&nbsp;

<h2 style="color: #000000;">
  <a title="Async" href="https://github.com/caolan/async" target="_blank">Async</a>
</h2>

###### <span style="color: #666666;">5833 packages</span>

Async is a utility package that provides powerful functions for working with asynchronous JavaScript. It supports usage with Node and the browser. Async allows you to process a block of data using a predefined function and deal with the results. This can be very useful for dealing with the opening and processing of multiple files. All these functions assume you follow the Node.js convention of providing a single callback as the last argument of your `async` function. I have yet to work with this library,as the library is built around async processing I feel something like <a title="Q " href="https://github.com/kriskowal/q" target="_blank">Q</a> or another promise library could be used instead.

&nbsp;

## <a title="Request " href="https://github.com/mikeal/request" target="_blank">Request</a>

<span style="color: #666666;">4905 packages</span>

Request a simple lightweight and easy to use http library, providing the standard http CRUD methods. The request developers boast that the library is the easiest to use, I have used this before on some project for talking to third party APIs. This has proved tricky when you run into same site origin errors, however this was due to the scenario that I was working with.  The below code shows how easy request is to use.  


##  <a title="Lo-Dash" href="http://lodash.com/" target="_blank">Lo-Dash</a>

&nbsp;

###### <span style="color: #666666;">3985 packages</span>

Lo-dash is another utility library that actually was the parent to the above mentioned underscore library. It contains many of the method&#8217;s such as map, each and some other advanced functions <span style="color: #222222;">for creating </span><a style="color: #222222;" href="http://hughfdjackson.com/javascript/why-curry-helps/">curried</a><span style="color: #222222;"> functions</span> and other patterns.  It has since become a superset of Underscore, providing more consistent API behavior, more features (like AMD support, deep clone, and deep merge), more thorough documentation and unit tests (tests which run in Node, Ringo, Rhino, Narwhal, PhantomJS, and browsers), better overall performance and optimizations for large arrays/object iteration, and more flexibility with custom builds and template pre-compilation utilities.

## <a title="Commander JS" href="https://github.com/visionmedia/commander.js" target="_blank">Commander</a>

&nbsp;

###### <span style="color: #666666;">3294 packages</span>

Commander is a on stop shop for command line integration with Node JS.  Following a method chaining structure commander allows you to pass options for the shell command. The library is strongly influenced by the Ruby <a title="Ruby Commander" href="https://github.com/visionmedia/commander" target="_blank">commander</a> gem. The main purpose of the commander package is to create a command line interface for your application. A very useful feature is the auto generation of help information and example is shown below:  

&nbsp;