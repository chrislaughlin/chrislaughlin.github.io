---
title: 'Belfast Ruby: Sidekiq, Ruby &#038; Life outside Rails'
author: chris
layout: post
permalink: /2014/05/12/belfast-ruby-sidekiq-ruby-life-outside-rails/
dsq_thread_id:
  - 2854287383
categories:
  - applications
  - development
  - technology
tags:
  - belfast
  - ruby
  - ruby on rails
  - ShopKeep
  - SideKiq
---
So it&#8217;s that time again <a href="http://belfastruby.com/" target="_blank">Belfast Ruby</a>! I unfortunately missed the last two meetup&#8217;s but was looking forward to this one, <a href="http://www.shopkeep.com/" target="_blank">ShopKeep POP</a> would be hosing the event in their Belfast offices. I have heard great things about Shopkeep and know one of their most recent hires, I have looked for a chance to have a snoop around for a while now.

The first talk was presented by Shopkeep&#8217;s <span style="color: #494949;">David Kennedy titled &#8220;An Adventure in <a href="http://sidekiq.org/" target="_blank">Sidekiq</a>: Millions of rows. One missing. Shenanigans!&#8221; , this talk would be a chance for David to walk through the very quick and basic install and configuration of SideKiq with some Shopkeep specific pro&#8217;s and con&#8217;s thrown in for good measure. SideKiq is background processing tool for Ruby it claims to be the best out, you can create a job that needs to be run and then pass this off to the background process which will then be handled by SideKiq. David used the example of a password re-set email that needed to be sent but not right away. David started the talk by explaining why Shoppkeep decided to go with this product over the others in the market such as Resque or DayledJob the main reason was performance, the open source nature of the product and the reliability.  </span>

<span style="color: #494949;">Talking through some examples and ways that Shopkeep use the product it was clear that it met all these requirements to the point that Shopkeep required an extra feature. The team as Shopkeep noticed that when processing large amounts of data through queues, they started to see large spikes of 502&#8217;s and other load related errors. They decided that it would be useful if they could pause one queue until the back log cleared then un-pause it. After a quick chat with the developer from Sidekiq they were told that it could not be done. However this was not going to stop them. With the pro version of the product middleware access is viable hence middleware path was created that would handle the pause process. Although a few days later the developers at Sidekiq released the same, which shows the care and support that is giving to the product. </span>

&nbsp;

The second talk was from <a href="http://www.sixdegreelabs.com/" target="_blank">Six Degree Lab&#8217;s</a> <a href="https://twitter.com/swmcc" target="_blank">Stephen McCullough</a> titled &#8220;Life outside of rails&#8221;, which gave an overview of other tools and that fit the rails job but at a quicker and more prototype style pace. Talking quickly about tools like Jekyll, Grape and Sinatra. Jekyll was talked about at a previous Belfast Ruby talks it allows you to run a web application up on your machine with only a few lines in the command line, it focuses on static sites and using markup to present your content. Grape allows you to build lightweight APIs with Ruby it&#8217;s a REST-like API micro-framework built to complement existing web application frameworks by providing a simple DSL to easily provide APIs. Sinatra is an open source software web application library and domain-specific language written in Ruby.  It does not follow the typical model–view–controller pattern used in other frameworks, such as Ruby on Rails. Instead, Sinatra focuses on &#8220;quickly creating web-applications in Ruby with minimal effort.

The night then ended with a quick chat from the people who help run and organise Belfast Ruby, talking about the future of the talks and proposed changes to the format. It is great to the see the not just the feedback of talkers and organisers but the community getting a chance to get evolved no matter how small. I&#8217;m still very new to ruby but would love to break my public speaking cherry in an event like Belfast Ruby, hopefully in the coming months the topic range is expanded as my ongoing work with JavaScript and its many frameworks and tools could give me a vast number of topics to speak on.

To keep up with Belfast Ruby check them out on <a href="https://twitter.com/belfastruby" target="_blank">Twitter</a>, <a href="https://github.com/belfastruby/belfastruby-website" target="_blank">GitHub</a> and <a href="https://groups.google.com/forum/#!forum/belfastruby" target="_blank">Google Groups</a>.

&nbsp;