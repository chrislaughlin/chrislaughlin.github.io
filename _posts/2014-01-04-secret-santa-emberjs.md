---
title: Secret Santa Emberjs
author: chris
layout: post
permalink: /2014/01/04/secret-santa-emberjs/
dsq_thread_id:
  - 2878665445
categories:
  - app
  - applications
  - code
  - development
  - javascript
  - Uncategorized
tags:
  - angular
  - bower
  - code
  - ember
  - githib
  - grunt
  - javascript
  - yeoman
---
After waking up one morning to a blue flashing light on my phone and came across a tweet from a fellow developer friend stating that EmberJs  was better than AngularJs and better preformant.

<blockquote class="twitter-tweet" width="550">
  <p>
    <a href="https://twitter.com/chrislaughlin">@chrislaughlin</a> Bold statement: I think EmberJs is better than AngularJs <a href="https://twitter.com/search?q=%23SHOCK&src=hash">#SHOCK</a> <a href="https://twitter.com/search?q=%23HORROR&src=hash">#HORROR</a> <a href="https://twitter.com/search?q=%23TRUEBILL&src=hash">#TRUEBILL</a>
  </p>
  
  <p>
    &mdash; Andrew McDowell (@madole) <a href="https://twitter.com/madole/statuses/416445884151234560">December 27, 2013</a>
  </p>
</blockquote>



<p style="text-align: left;">
  <span style="line-height: 1.5em;">I also thought that this was a bold statement as both of us had worked deeply with a large-scale AngularJs application and I have knocked out a number of AngularJs applications on this blog for a while. So after some time I had progressed some more on my other projects such as the </span><a style="line-height: 1.5em;" title="Secret Santa: Any excuse to use JavaScript" href="http://www.christopherlaughlin.co.uk/2013/12/15/secret-santa-any-excuse-to-use-javascript/">Secret Santa web app</a><span style="line-height: 1.5em;">. So after much thought it was time to give Ember a try and the best way to compare with Angular is to build the same application, as the secret santa was still fresh in my mind I decided to create this again using ember. To also keep the competition fair I would use a YEOMAN generator as this was used with the Angular version.</span>
</p>

&nbsp;

## Getting Started

To kick things off I had a search for a <a title="EmberJs YEOMAN Generator" href="https://github.com/yeoman/generator-ember" target="_blank">Ember generator</a> which didn&#8217;t take long to find, there was a generator which looked very similar to the Angular one I had used before. So now it was time to follow the instructions on the site.

The install process was the same as the Angular generator however for one change there was a step that needed grunt-mocha to be installed, grunt-mocha is the tool of choice for testing the server-side code in the application. This was not included in the other generators that I had used. I was interested to learn more about mocha as in my past I had only used Jasmine. One other difference that i noticed when the generator ran I was only prompted about the install of bootStrap with SASS, I was not asked for the name of the project/app which was strange as this would help define the namespace for the application.

This is very important when using Angular as you need to add modules and services to the application via the application name. It also helps to give a level of structure to the application. So now I have the basic demo application setup the first test is grunt server will the application run first time&#8230;&#8230;&#8230;..

As you can see below it has worked one thing to note I opted to install twitter bootstrap using SASS which has a dependency on compass and this needs ruby, I ran unto this problem when using the Angular generator for YO. I managed to find some stack overflow answers on this and for the life of me cannot remember them but I&#8217;m sure some smart google searches will get you the help needed.

[<img class="size-medium wp-image-1609 aligncenter" alt="Screen Shot 2014-01-04 at 16.29.42" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/01/Screen-Shot-2014-01-04-at-16.29.42-400x250.png" width="400" height="250" />][1]

&nbsp;

So now the application in running its time to look at the structure and code to see how hard it will be to create the secret santa application.

&nbsp;

## Looking at the Code

So having a look through the project I started with the package.json file that was generated, it looks like the yo generator was smart and had taken the folder name removing any hyphens and converting it into camelcase everything else is very standard including the grunt file and the bower config.

Looking into the Ember code now since i come from an Angular background the first place I look is the app.js file this will give me a very low-level look at the application and an idea of what&#8217;s going on.  It&#8217;s very different from what I&#8217;m used to, it references the controllers, views, models and routes out of the box even if there are none.

&nbsp;

## Where is the rest of the code ?

It took me a few minutes to discover that there was no real Ember code added by the generator, all the generator seemed to have built was a semi static site that loaded some values in from a hard-coded array. This sucked as I was unable to see Ember at work and try to learn around this way, so it looks like ill have to start off again with the ember guide. To be fair the generator has been useful setting up grunt and other tools for me as they can be a pain if you don&#8217;t know them inside out, which I don&#8217;t.

So this is where the blog will stop for the mean time until I can get a basic understanding of the Ember code and then the development will start again.

 [1]: http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/01/Screen-Shot-2014-01-04-at-16.29.42.png