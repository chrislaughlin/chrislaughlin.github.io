---
title: 'Secret Santa: Any excuse to use JavaScript'
author: chris
layout: post
permalink: /2013/12/15/secret-santa-any-excuse-to-use-javascript/
dsq_thread_id:
  - 2853463562
categories:
  - applications
  - apps
  - development
  - javascript
tags:
  - Christmas
  - development
  - grunt
  - javascript
  - node
  - yeoman
---
So its been a while since I&#8217;ve blogged but work has picked up and the social life has taken over. It getting close to Christmas and as you probably know already I&#8217;m the tech monkey for the Belfast based artist group <a title="LOFT Belfast" href="http://loftbelfast.co.uk" target="_blank">LOFT</a>, any every year I take on the stressful role of organizing the secret santa event.

Last year I had used a third-party web-based tool that let you enter the names and email addresses of the group members, this tool then carried out the mixing and assigning of names so that everyone would get a match email telling them who they had to get a present for. However this went terribly wrong with some people getting the same match as another member, most of the emails went into junk folders and some emails did not arrive at all. Luckily we were able to pull everything together and make sure that everyone got a gift.

&nbsp;

This year I was going to learn from my mistakes, I have grown my knowledge in JavaScript, <a href="http://angularjs.org/" target="_blank">AngualrJS</a>, <a href="http://nodejs.org/" target="_blank">NodeJS</a>, <a href="http://www.mongodb.org/" target="_blank">MongoDB</a> and Grunt so this would be the perfect time to put the skills I have built up to some use before they are forgotten. I decided that I work create a simple web app that would allow the LOFT members to enter their email address and see their match. The site would also allow them to see the match anytime so the fear of losing the email containing the match or not receiving the email was gone.

[<img class="size-medium wp-image-1602 aligncenter" alt="toolset" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2013/12/toolset-400x160.png" width="400" height="160" />][1]

I decided that since this would more than likely only get used one a year and maybe never again I did not want to reinvent the wheel. I Choose to use the <a href="yeoman.io" target="_blank">YOMAN</a> tool for getting the application up and running, this also proved as a chance to trial the tool as I had never used it for an actual project. I had looked into the tool before on an old project but it was still gathering support and still needed work. Yeoman is a mix between package manage, dependency injection, scaffold workflow and build tool, well Yeoman is not all these things but more of a stack that has all the three tools that take care of this are:

*   [Yo][2] scaffolds out a new application, writing your Grunt configuration and pulling in relevant Grunt tasks that you might need for your build.
*   [Grunt][3] is used to build, preview and test your project, thanks to help from tasks curated by the Yeoman team and grunt-contrib.
*   [Bower][4] is used for dependency management, so that you no longer have to manually download and manage your scripts.

&nbsp;

Yo can use many generators, this generate the project and file based on a scaffold, the generator I decided to use was the <a href="https://github.com/DaftMonk/generator-angular-fullstack" target="_blank">angular-full-stack</a> this would generate the perfect application that would suit my needs. An express (nodejs) application that would handle the server-side processing, mongoose for handling the mongoDB processing, twitter bootstrap for the front end, angularJS for the client-side processing, phantomJS and Jasmine for testing and finally Grunt for keeping everything running together. The generator also includes a process for deploying to a heroku instance I wasn&#8217;t interested in this as I would be running the app on my server but this process does work and is very easy to use as seen <a href="http://tranquil-peak-2732.herokuapp.com/#/" target="_blank">here</a>(If the app hasn&#8217;t gone to sleep you should see the stock angular app from the Yo generator).

The process of using the generator is very easy and its best to follow the steps on the github repo this will take you through the full process of creating the application and building up the features you need, from there its yours for the making. The current feature list for my application is below:

*   Store the email to name match list (hard-coded in an Angular JS service for now, mixing code was third-party)
*   Allow user to enter their email address and receive a match 
    *   Process email address to insure matching happens e.g. trim and validate
    *   If no matches are found then return error message

Below are the proposed features for the next version hopefully developed for next Christmas:

*   Allow admin (secret santa organiser) to enter member details and do matching
*   Store matches in a mongoDB instance (most likely mongoLabs)
*   Store multiple lists
*   Allow admins to clear lists and restart matching in cases when member lists change
*   Increase security for finding matches now anyone who knows emails can find matches
*   Improve look and feel of the application.

I will hopefully get some time over the year to get the above features implemented and will keep the blog up to date with them. If you want to see the current app for yourself you can have a look <a href="http://christopherlaughlin.co.uk/santa/" target="_blank">here</a> or checkout the git repo <a href="https://github.com/chrislaughlin/secret-santa" target="_blank">here</a>.

&nbsp;

&nbsp;

 [1]: http://www.christopherlaughlin.co.uk/wp-content/uploads/2013/12/toolset.png
 [2]: https://github.com/yeoman/yo
 [3]: http://gruntjs.com/
 [4]: http://bower.io/