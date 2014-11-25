---
title: 'Development, Deployment &#038; Collaboration at Etsy &#8211; Qcon London 2014'
author: chris
layout: post
permalink: /2014/03/12/development-deployment-collaboration-at-etsy-qcon-london-2014/
dsq_thread_id:
  - 2906333582
categories:
  - Uncategorized
---
The first technology talk of my trip in <a href="http://qconlondon.com/" target="_blank">Qcon London</a> was presented by <a href="https://twitter.com/mrtazz" target="_blank">Daniel Schauenberg</a>, an infrastructure and tool smith at <a href="http://www.etsy.com/" target="_blank">Etsy</a>.

> &#8220;At Etsy about 150 engineers deploy a single monolithic application more than 60 times a day.&#8221;

These figures made me step back and think could this be real or is this a *proposed* solution that has never worked? I can&#8217;t possibly see this work with a development to live deployment system. However as the talk progressed this became true and I could see how this was possible with the correct tool set and attitude. At the time of creating the slides, Etsy had **60 million** monthly visitors, **1.5 billion** monthly page views and averages **50 deployments** a day!

<p style="text-align: left;">
  The best way to find out if you have the infrastructure to handle this is to ask yourself the following question <em>&#8220;how comfortable are you with deploying a change right now?&#8221;. </em>In most cases the answer is not very comfortable. Not to fear &#8211; I agree with that. At Etsy it&#8217;s not so much the change but the size of the change. The term small change is used a lot here. With a mix between small changes and configuration flags, deployments can be performed at any time with very low risk to the application and users. The work environment at Etsy provides a brilliant learning ground as mentioned by Daniel, <em>&#8220;if it&#8217;s your first day at Etsy you deploy the site&#8221;</em>.  For most people (myself included) this would be a terrifying experience. First days are normally very stressful, but then also having the responsibility of deploying the sole product that the company offers is taking it too far.
</p>

<p style="text-align: left;">
  <a href="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/03/CI-at-Etsy.jpg"><img class=" wp-image-1642 aligncenter" title="Development and Deployment at Etsy" alt="CI at Etsy" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/03/CI-at-Etsy-e1394487042387-333x500.jpg" width="200" height="300" /></a>
</p>

But as you have guessed the team at Etsy have made this an extremely smooth and simple process. The entire application stack can be run on a generated VM. All developers use these VMs to provide consistency across the team. The CI is also handled by a VM &#8211; a cluster of build VMs running <a href="http://jenkins-ci.org/" target="_blank">Jenkins </a>are used to run the test suite and all other associated tests, freeing up the development VM for new workloads. Once all the tests have passed you are able to then move onto what they call the *&#8220;deployment train&#8221;* and use the in house developed and open sourced deployinator. <a href="https://github.com/etsy/deployinator" target="_blank">Deployinator </a>gives two simple buttons &#8211; &#8220;run tests&#8221; and &#8220;deploy&#8221;.  This allows the developer to quickly deploy and get on with the next block of work.

So the change is deployed.  What now ? well at Etsy they take pride in the fact that everything can be monitored. Once a build goes live, you then watch a number of tools including <a href="https://github.com/etsy/supergrep" target="_blank">supergrep </a>and the monitor dashboard for any flux or strange change. This will usually indicate if something was missed in testing and if there is a bug. The strong &#8220;on call&#8221; policy means that nothing is missed when the graphs or logs start to go crazy. Everyone works a monthly rotation for &#8220;on call&#8221; and often for different departments.

One aspect I forgot to mention at Etsy is the use of IRC for almost all communication. There is a channel for everything and probably the most important is #warroom. The &#8220;war room&#8221; is for build issue resolutions. Daniel talks about how this is a place where issues are analysed, resolved and a perfect place to &#8220;lurk&#8221; if you&#8217;re new and want to see pro&#8217;s at work. This is another place where the learning attitude at Etsy shines through. New joins and junior developers  are encouraged to watch in rooms while people are working on an issue to let them see the thought process and pick up tips and tricks that other developers have homed over the years.

The last part of CI process which I loved and want to try out on my own project is the &#8220;post mortem&#8221; &#8211; This takes place after the live issue has been resolved and is an open blameless forum where the team can discuss the issue. A large part of this process is not *&#8220;who did this?&#8221;* but *&#8220;what can we learn from this?&#8221;.* I think this step is missing from many projects. It&#8217;s great to say* &#8220;we had an issue in live, it&#8217;s fixed now&#8221;* but without digging into the cause and the prevention. Issues like this will regress and continue to be a problem. Other points I took away from the talk included; a good development/deployment culture is an on going effort and will never be perfect, encouragement of learning is an extremely important task, share everything and lunch &#8216;n learns (which I will be trying to implement).

In summary the talk was a very insightful look into the processes and life of a large and successful development team. I came away with many thoughts and suggestions for my own team and finally have learned more about the development, deployment and continuous integration cycle than I expected. A big thanks to Daniel for taking time to present the talk.

&nbsp;