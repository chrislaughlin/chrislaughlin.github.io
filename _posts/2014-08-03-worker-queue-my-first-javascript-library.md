---
title: 'Worker Queue: My First JavaScript Library'
author: chris
layout: post
permalink: /2014/08/03/worker-queue-my-first-javascript-library/
dsq_thread_id:
  - 2897077223
categories:
  - applications
  - code
  - development
  - javascript
tags:
  - angularjs
  - github
  - javascript
  - processing
  - queue
---
## Background

While working on a project for a customer I had to develop some code that would handle the validation of products a user was adding and configuring. The products could have up to 100 attributes and relationships to other products with a large amount of validation criteria. A need was to have the validation process in the background while the user configured and carried out other actions, the validation would change the colour of icons on the screen. Unfortunately I had support Internet Explore (*for reason ill not get into*) and this meant I was quickly going to run into JavaScript issues. My first approach was to just take each product loop through them and call the required validation functions. This worked fine via Chrome and was very quick to complete, even when the user was carrying out other action that required JavaScript. However when trying the same in Internet Explore I ran into the dreaded long running script error.

[<img class="size-medium wp-image-1826 aligncenter" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/08/stoprunningscript1-400x201.png" alt="stoprunningscript1" width="400" height="201" />][1]

After profiling the page it seemed that the processing of the product including the validation functions were not causing the issue it was more related to the amount of products and the time taken to process them all. The fact that this needed to be done once the page loaded caused a lockup on the screen which prevented the user from carrying out any actions until the validation finished. I tried to reduce the processing and add JavaScript performance improvements. But this only meant that the code would handle a little more products each time I always reached a point were I would see the script error again.

## The Solution

The best solution was to introduce a &#8220;*multi-threaded*&#8221; style service that would allow me to process the products without creating a bottle neck in the application code. It&#8217;s well-known JavaScript is single threaded so a real multi-threaded approach is not possible. The customer project in question was using Angular JS for the front end application code so I built an angular service. The service was built around the idea of using timeouts to delay the processing of the JavaScript. The service provided the ability to create a queue and set a function for processing then push items into the queue.

That takes us to now, I have recently been trying to branch out my JavaScript skills and contribute more to the community so I decided to provide the queue processor as a library, As it was originally an angular service it ported very easy I was also able to add more features such as delete queue and being able to set the delay. I followed <a href="http://code.tutsplus.com/tutorials/build-your-first-javascript-library--net-26796" target="_blank">Andrew Burgess</a> post on creating a JavaScript library to help me build up the needed code for exposing the functions.  You can see a very basic example below:  
  
You can check out the code from <a href="https://github.com/chrislaughlin/worker-queue" target="_blank">GitHub</a> to see the inner workings and how the processing is done, you can also install the Worker Queue from bower by following the instructions on the GitHub page. I hope to use the worker queue in future projects and hope to add more features.

Please check the code out let me know what you think and hopefully it will provide some use to other people.

 [1]: http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/08/stoprunningscript1.png