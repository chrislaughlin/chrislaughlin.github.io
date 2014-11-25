---
title: 'Twit: Twitter made easy for Node.js'
author: chris
layout: post
permalink: /2013/10/10/twit-twitter-made-easy-for-node-js/
dsq_thread_id:
  - 2852441785
categories:
  - applications
  - code
  - javascript
tags:
  - github
  - javascript
  - node
  - npm
  - projects
  - twit
  - twitter
---
So I came across an interesting blog post about getting a node.js twitter bot up and running in under 20 minutes. From this I decided that I would try out my own working with [Twit][1] and see how easy it is to get started with Twitter and [node.js.][2]

First step was to install the Twit package, this was easy via npm with the following command:

<pre style="text-align: left; padding-left: 60px;">npm install twit</pre>

<p style="text-align: left;">
  <p style="text-align: left;">
    This should install Twit into a node_models folder in your project, the next step it to get your twitter application set up. For this i created a test twitter account and linked an application to it, you can create the application linked to the twitter account on the twitter developer site. Once you have created the account you will need to generate tokens for the application make when doing this that you ensure in the application settings that you select read and write as you twitter bot will most likely need to post to twitter. These tokens are used for the oauth authentication that is used for all communications to and from twitter.
  </p>
  
  <p style="text-align: left;">
    Once this is all done you can start the development, for this blog post ill run though what i have developed so far and hopefully continue the post updating on the changes and advancements to the code (so this code will be untested and rough). For I started by creating a server.js file this will be my main node.js file, for the time being I will have all my code in this but will plan to break out into different modules are time and code grows.
  </p>
  
  <p style="text-align: left;">
    To start you need to define Twit as a &#8220;class&#8221; so as how things are done in Node.js we &#8220;require&#8221; the twit package.
  </p>
  
  <p style="text-align: left;">
  </p>
  
  <p style="text-align: left;">
    Also in this block of code we set up the Twit instance T with the access to the twitter user account. next we want to be able to post to a time line, this will test if everything actually works. For this we Twit post function that allows a uri for when to post and params e.g. status, as shown below
  </p>
  
  <p style="text-align: left;">
  </p>
  
  <p style="text-align: left;">
    <p style="text-align: left;">
      So from the code you see that we build a string with the date time string this is used to get around a constraint on the status post that doesn&#8217;t allow duplicates in quick succession. We end call T.post and pass in the status uri and the text inside a param. As this essentially is a http.post in the backround we get can pass in a call back funtion. This will get run once the http request has been completed. We will want to get the err (error) if there is one and the reply as the reply will contain data on the tweet that was just posted.
    </p>
    
    <p style="text-align: left;">
      The last part of code is of course getting tweets, for this I thought that instead of the standard get my timeline or my home time (also my account has no followers and is following no one) I thought that it would be best to try a search. I also know that later on I will be wanting to explore the search in more detail so the more practice the better.
    </p>
    
    <p style="text-align: left;">
      The below shows how to search for a term and return and display the last 10 tweets with that search term.
    </p>
    
    <p style="text-align: left;">
    </p>
    
    <p style="text-align: left;">
      This was probably the most tricky due to the lossy typed nature of JavaScript and JSON without knowing the data structure its hard to know what you&#8217;re looking for although the <a href="https://dev.twitter.com/docs/api/1.1/get/search/tweets">twitter dev guides</a> are very useful. This code will then return something like this.
    </p>
    
    <p style="text-align: center;">
      <a href="http://www.christopherlaughlin.co.uk/wp-content/uploads/2013/10/Screen-Shot-2013-10-10-at-23.08.45.png"><img class="alignnone size-medium wp-image-1588" alt="Screen Shot 2013-10-10 at 23.08.45" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2013/10/Screen-Shot-2013-10-10-at-23.08.45-400x116.png" width="400" height="116" /></a>
    </p>
    
    <p style="text-align: left;">
      Some from here I have so far managed to post a status and read a search of statues. Im hopping for the next step to push the token details in to a config class of some sort. Then make a start on a simple UI that will allow me to carry out the actions through a web UI and see the results in a browser. In the mean time all code is being kept in the following github repo and will hopefully be kept up todate.
    </p>
    
    <p style="text-align: left;">
      <a href="https://github.com/chrislaughlin/nodetwitterbot">https://github.com/chrislaughlin/nodetwitterbot</a>
    </p>
    
    <p style="text-align: left;">

 [1]: https://github.com/ttezel/twit
 [2]: http://nodejs.org/