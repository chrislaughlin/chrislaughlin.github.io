---
title: 'Jasmine, Grunt, and jasmine_node: testing via a build task'
author: chris
layout: post
permalink: /2013/10/19/jasmine-grunt-and-jasmine_node-testing-via-a-build-task/
dsq_thread_id:
  - 2853241191
categories:
  - app
  - applications
  - development
  - javascript
tags:
  - grunt
  - jasmine
  - javascript
  - node
---
So continuing on from my last post using Twit with node js. This post covers the work need to get jasmine set up to test the server application.

Wanting to take on the workflow of TDD (test driven development)  I decided to use [jasmine][1] as my test framework, for this I used [jasmine-node][2], this is a node package configured for node projects. Jamsie node can be installed using the following command:

<p style="text-align: center;">
  npm install jasmine-node
</p>

<p style="text-align: left;">
  Once installed test files can be created, to get started I created a few simple tests that would make requests to the application and rest the responses, shown below:
</p>

<p style="text-align: left;">
</p>

<p style="text-align: left;">
  These two tests use the node module &#8220;request&#8221; this makes a http request then the result is inspected, once this file has been created it can be run using the following command.
</p>

<p style="text-align: center;">
  jasmine-node &#8211;verbose &#8211;captureExceptions server/test/spec/
</p>

<p style="text-align: left;">
  The command is calling the installed tool jasmine-node then using the &#8211;verbose option to show all details printed by the tests and any errors, captureExecptions will show any errors and stack traces which fail before the &#8220;expect&#8221; function in the code this will show the error if the test fails before the expect.
</p>

<p style="text-align: left;">
  Once jasmine was installed and set up to run tests I wanted to add this to the build process so I decided to install grunt, using the following command.
</p>

<p style="text-align: center;">
  npm install grunt
</p>

<p style="text-align: left;">
  Once grunt is installed I then needed to create a Gruntfile.js file, this will hold all the configurations and grunt commands that can be used for the project. As I want to use grunt to run jasmine I looked and found that there is grunt plugin for jasmine-node, I then installed this using the following command:
</p>

<p style="text-align: center;">
  npm install grunt-jasmine-node &#8211;save-dev
</p>

<p style="text-align: left;">
  This will install the grunt jasmine-node plugin and also add this to the dev dependencies in the package.json once installed the next process is to created and config the grunt file shown below:
</p>

<p style="text-align: left;">
</p>

<p style="text-align: left;">
  The gruntfile starts with the module definition then the grunt commands that can be used for this case the only command is the jasmine-node command. Once set up I was able to run the test via the following command:
</p>

<p style="text-align: center;">
  grunt jasmine_node
</p>

<p style="text-align: left;">
  This will come in handle once the project is running on a CI (continuous integration) server as it will allow the tests to be run as part of the build task.
</p>

&nbsp;

 [1]: http://pivotal.github.io/jasmine/
 [2]: https://github.com/jasmine-contrib/grunt-jasmine-node