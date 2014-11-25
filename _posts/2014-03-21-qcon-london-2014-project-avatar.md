---
title: 'Qcon London 2014: Project Avatar'
author: chris
layout: post
permalink: /2014/03/21/qcon-london-2014-project-avatar/
dsq_thread_id:
  - 2853540396
categories:
  - applications
  - javascript
  - technology
tags:
  - avatar
  - java
  - javascript
---
<a href="https://avatar.java.net" target="_blank">Project Avatar</a> tackles the solution of providing a robust and extendable thin server client, with server-side data services in both Java and JavaScript. The server-side logic does not only use JavaScript but can also utilise Java libraries to offer a full stack solution. The typical stack for an Avatar application comprises of a data layer which can be interchangeable e.g. NoSql, SQL or Graph while the server has many elements including:

*   <a href="http://openjdk.java.net/projects/nashorn/" target="_blank">JDK 8 (Nashorn)</a>  java framework server runtime
*   Avatar Compiler
*   Avatar Runtime
*   Application Views: 
    *   Node Modules
    *   Avatar JS
*   REST 
    *   Avatar Modules
    *   Application Services

Finally the client which can also be interchanged however the recommended stack includes HTML5, CSS3 and any number of JavaScript MVC frameworks. The server-side views can also be interchanged with client side views based on the project needs.

## Avatar Services

An Avatar service is similar to the Java servlet model but has more focus on the clients needs, the service implementation can leverage Node modules, third-party modules and due to the support in Java 8 can have direct invocation of Java code including  a rich set of Java libraries.

## Concurrency

An Avatar JS application is similar to Node in the sense that it is asynchronous and single threaded, however Avatar extends this to enable multiple threads. Each in isolation with a set of JavaScript objects with requests load balanced by the framework. Avatar uses an &#8220;actor-like&#8221; concurrency model which uses multiple threads with no shared data that communicate via messages. Currently the messaging system supports scalable communication across multiple threads but future development will see this extended to support both the browser and clustered server nodes. The integration of JavaScript and Java allows the sharing of mutable Java objects across threads assuming that they are thread safe. Avatar also provides JavaScript code to handle blocking Java code to ensure that all code is async.

## Getting Started and Example

Getting up and running with Avatar is a simple process, the first step is to get the early release of <a href="https://jdk8.java.net/" target="_blank">Java 8</a> <a href="https://jdk8.java.net/download.html" target="_blank">JDK</a>. I&#8217;m running on Mac OSX Maverick so I just needed to installed the dmg image file. Next step is to install <a href="http://download.java.net/glassfish/4.0/release/glassfish-4.0.zip" target="_blank">GlassFish server </a>this will handle the deployment of the Avatar application, Glassfish is an open source  Java EE application server. Installing Glassfish is as simple as the Java 8 JDK just run the image file you downloaded then its time to install Avatar. So after downloading the <a href="https://avatar.java.net/builds/1.0-ea/avatar-1.0-ea.zip" target="_blank">Avatar</a> install file run the following command:

> unzip -d glassfish4/glassfish avatar-1.0-ea.zip

The above command is saying that we want to un-zip the avatar file into the Glassfish installation directory, after this finishes you will need to configure the needed environment variables as shown below:

> export AVATAR_HOME=/Users//glassfish install>/glassfish4/glassfish
> 
> PATH=$PATH:$AVATAR_HOME/bin

Now Avatar is set up you can test this by running &#8220;Avatar&#8221; from the command line and you should see some help text. Now lets create a simple test application, to do so run the following commands:

> avatar new &#8211;example=hello

This creates an example application in a directory called &#8220;hello&#8221; thats how simple the process is, but how do we run the application?

> asadmin start-domain
> 
> asadmin deploy hello

Once finished you can then go to  <http://localhost:8080/hello> to see you application running on your Glassfish server as shown below:

[<img class="size-medium wp-image-1652 aligncenter" alt="Screen Shot 2014-03-16 at 13.13.09" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/03/Screen-Shot-2014-03-16-at-13.13.09-400x250.png" width="400" height="250" />][1]

&nbsp;

It&#8217;s very basic but its the first Avatar application running on your machine, time to go for a beer to celebrate.

 [1]: http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/03/Screen-Shot-2014-03-16-at-13.13.09.png