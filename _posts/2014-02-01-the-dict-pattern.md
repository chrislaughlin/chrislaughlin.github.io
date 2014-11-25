---
title: The Dict Pattern
author: chris
layout: post
permalink: /2014/02/01/the-dict-pattern/
dsq_thread_id:
  - 2870592972
categories:
  - javascript
tags:
  - database
  - javascript
  - map
  - mongodb
  - reddit
---
So after a long day in work looking through the <a href="http://www.reddit.com/r/javascript/" target="_blank">JavaScript subreddit</a> I came across a post about <a href="https://github.com/louischatriot/nedb" target="_blank">NEDB (Node Embedded database)</a> its a persistent database for Node.js written in JavaScript with no dependances, its described as SQLite for Node.  It targeted towards small projects that need a on system database that does not need to be clustered or managed, It takes some API&#8217;s and implementation from MongoDB.

However once looking into this I could not see any real life usage for this (for me at least) with the ease of use of MongoDB locally and remotely I would go for Mongo when I need database storage. So onto the point of this post in the comments of the <a href="http://www.reddit.com/r/javascript/comments/1wk7w4/nedb_a_pure_javascriptimplemented_database/" target="_blank">post</a> a lot of people agreed with me but some people mentioned that an easy way to have a persistent data source made totally from JavaScript was to use the var db = Object.create(null);  but looking at this why couldn&#8217;t you use the var db = {};.

However after looking into this there are a number of differences between the Object create method and the basic {} method. When using an object as a map you will encounter some issues such as the following:

<!-- Missing Gist ID -->

The reason the above evaluation does not return the expected is due to the prototype methods in JavaScript so in this case the {} object has a toString and hasOwnProperty prototype function so in the off chance but you can&#8217;t guarantee some data ended up checking your map for &#8216;toString&#8217; it might not return the results you expect. the correct method is to use Object.create as this will create an object map with out any prototype functions, as shown below:

<!-- Missing Gist ID -->

Although the above is the best method its always recommended to use a library as this will be fully tested an manage the memory better.

&nbsp;

&nbsp;