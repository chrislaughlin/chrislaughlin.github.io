---
title: 'Qcon London 2014: BladeRunnerJS'
author: chris
layout: post
permalink: /2014/03/30/qcon-london-2014-bladerunnerjs/
dsq_thread_id:
  - 2860672705
categories:
  - applications
  - javascript
tags:
  - bladerunner
  - grunt
  - javascript
  - qconlondon
  - yeoman
---
<a href="http://bladerunnerjs.org/" target="_blank">Blade runner JS </a>is a JavaScript framework that focuses on getting up and running quickly and creating independent features that combine to form a full application. Blade runner JS provides not only a scaffolding command line tool but a web-based dashboard that allows the developer to create, developer and test modules of a large application without having to run of the full application stack.

The framework focuses on &#8220;blades&#8221; a blade is a feature, module or part of the web application e.g navigation menu, form, map area etc. The developer can create a blade either using the command line tool or the web dashboard, then develop the blade without thinking about other blades in the application. This provides many advantages such as cutting out the load time when refreshing a whole web application or having to navigate through layers of authentication or complexity to visualise the part of the application that the blade belongs to. Blades talk to each other using messages, this is what makes the blades independent, when developing the blade all the developer has to think about is what input is needed and what output is needed. This also provides the perfect environment for testing as the complexity of mocking data requests and responses has been cut down. The web dashboard also provides logging output to show all the transactions to and from the blade, showing the data in the messages.

The only issue I had after looking into Blade Runner, was that although there is nothing out there already that does the same out of the box it can be achieved. With the existing tool out at the moment like YEOMAN and Grunt the same tasks could be carried out e.g. being able to scaffold a web application through the command line.  With the advancements of the YEOMAN generators most application types and styles are scaffold for you already, including helper commands. To create the &#8220;blades&#8221; would just need to be a development decision for the project,  this could be achieved via Angular JS using the emit/broadcast/on functions. This would allow different modules of you application talk to each other the same way that the blades talk to each other. The only part missing from the custom solution is the web-based dashboard this where I credit the team in at blade runner as the web dashboard is a very useful tool for not only developing but testing application. This would be hard to hand wire yourself into a custom YEOMAN/Grunt solution.

My overall view on Blade Runner JS is mixed, the team have progressed and created a framework that fixes an existing and prolific problem in large-scale single page web application development. However although most of the framework already existed in other forms and are being used by a large community. I see potential in some aspects of the framework and can see it progressing with more advanced features and growth into other use cases.  I would recommend <a href="http://bladerunnerjs.org/docs/use/getting_started/" target="_blank">downloading</a> and giving it a try.