---
title: 'Review: Codio Cloud Based IDE'
author: chris
layout: post
permalink: /2014/05/17/review-codio-cloud-based-ide/
dsq_thread_id:
  - 2854287308
categories:
  - applications
  - code
  - development
  - review
tags:
  - codio
  - ember
  - express
  - javascript
  - node
---
So ever since I got a Chromebook I have been mainly using it for quick browsing (when a phone wont do), taking notes when at events or talks and blogging from.  I had heard of cloud based editing and development for ages, I&#8217;m a large fan of <a href="http://jsfiddle.net/" target="_blank">jsFiddle</a> other light weight editors but never though about taking the full development experience into the cloud. I have always felt that the machine installed applications like Intellij, Web Storm or Visual Studio can&#8217;t be beaten by a browser. So when I stumbled across a promoted tweet from <a href="https://codio.com/" target="_blank">Codio</a> I couldn&#8217;t pass up the chance to have a good and maybe have my views changed.

## Getting Started

First impressions always count and Codio did not disappoint, a night page listing its features etc then the gold, pricing and sign up. There are two plans the FREE plan that only allows public editing e.g anyone can see what you are working on (I assume that does not mean anyone can edit) and the other os paid which allows you to make the edits private. I of course opted for the free version much like all services I use, since I would be using it for projects I host publicly on Github there is not much point making it private. Speaking of Github, this can be used as the authentication method which works perfectly as most of the time my browser is logged into Github.

## Getting your Edit On

So you have an account what now,  create a project to work on. For this review I decided to opt for an existing repo that I have blogged about before [Meal <span style="text-decoration: underline;">Finder</span>][1].  As you can see from the below screen shot you have number of options for getting you project stated from git, a template, mercurial, zip, FTP and sales force.

<div id="attachment_1759" style="width: 410px" class="wp-caption aligncenter">
  <a href="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-15-at-21.15.02.png"><img class="wp-image-1759 size-medium" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-15-at-21.15.02-400x358.png" alt="Screen Shot 2014-05-15 at 21.15.02" width="400" height="358" /></a><p class="wp-caption-text">
    Codio: New Project Page
  </p>
</div>

&nbsp;

From here I have the project a name and pasted in the git link for Meal Finder, once created you are presented with the repo&#8217;s readme file. When first doing this I couldn&#8217;t work out if this was a web view of the repo but once looking around I could see the familiar project planner and knew where I was.

<div id="attachment_1760" style="width: 410px" class="wp-caption aligncenter">
  <a href="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-15-at-21.19.16.png"><img class="wp-image-1760 size-medium" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-15-at-21.19.16-400x187.png" alt="Screen Shot 2014-05-15 at 21.19.16" width="400" height="187" /></a><p class="wp-caption-text">
    Codio: Project View
  </p>
</div>

&nbsp;

The code editor is very smooth, some of the features out of the box that really impressed me include auto save, code completion and syntax highlighting. The project I was using was a NodeJS and EmberJS application everything was recognised except the handlebars code. However for the project the handlebars code was placed in the index.html file inside script tags so i was not expecting this to work as this is not fully supported in Web storm.  The file menu along the top of the page also gives some great features almost all working as they would in an installed IDE such as find (which all developers use).

<div id="attachment_1761" style="width: 251px" class="wp-caption aligncenter">
  <a href="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-15-at-21.26.39.png"><img class="wp-image-1761 size-full" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-15-at-21.26.39.png" alt="Screen Shot 2014-05-15 at 21.26.39" width="241" height="264" /></a><p class="wp-caption-text">
    Codio: Find Menu
  </p>
</div>

&nbsp;

The style and layout reminded me of Sublime Text at points I have feeling that some notes were taken from this. The command bar is a very big give away as this is taken right out of Sublime.

<div id="attachment_1762" style="width: 410px" class="wp-caption aligncenter">
  <a href="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-15-at-21.30.38.png"><img class="wp-image-1762 size-medium" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-15-at-21.30.38-400x324.png" alt="Screen Shot 2014-05-15 at 21.30.38" width="400" height="324" /></a><p class="wp-caption-text">
    Codio: Command Bar
  </p>
</div>

## Building And Deploying

So it&#8217;s all good being able to edit the code but its nice to be able to deploy and test what changes you have made. Codio has a terminal built into the IDE which supports node.

<div id="attachment_1764" style="width: 410px" class="wp-caption aligncenter">
  <a href="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-17-at-18.26.17.png"><img class="wp-image-1764 size-medium" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/05/Screen-Shot-2014-05-17-at-18.26.17-400x160.png" alt="Screen Shot 2014-05-17 at 18.26.17" width="400" height="160" /></a><p class="wp-caption-text">
    Codio: Terminal
  </p>
</div>

&nbsp;

Out of the box the you get node and npm for running you application, the terminal runs fast and handle all the unix commands you would expect. Within a few minutes I had run npm install to get all the dependencies for the application installed, then installed bower and was able to run up the application. So the application running and express is hosting a static page with my ember application everything should be fine but nothing is that easy. I used bower for installing components like handle bars and jQuery but on first start the application could not see all the bower components. It was strange that some were detected but not all, looking at the project structure I couldn&#8217;t see the bower components folder and running any bower commands did not give any output in the terminal. This meant that the app could not run fully as ember would not start without handle bars. I had to resort to using download files instead of bower. Once the node application is started you can view the application by viewing the box url.

## Conclusion

Over all the user experience of Codio was great, being able to take a project hosted somewhere else and make changes. Although I only spent a short time when working with the view of reviewing the tool I was really impressed, the fact that everything worked like an on machine IDE. I was surprised with the speeds that the terminal worked and the code completion. The issues with bower let me down a little and made me think twice about how I could build the project. I plan to use the tool more and more to try to get the best out of the Chromebook. I plan to try the git integration and templates in the future.

&nbsp;

 [1]: http://www.christopherlaughlin.co.uk/2014/04/24/meal-finder-ember-full-stack-data/ "Meal Finder: Ember Full Stack Data"