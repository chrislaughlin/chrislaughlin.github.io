---
title: Scroll Path
author: chris
layout: post
permalink: /2012/05/14/scroll-path/
dsq_thread_id:
  - 2869259742
categories:
  - javascript
  - Uncategorized
tags:
  - canvas
  - github
  - html5
  - javascript
  - jquery
---
So a few weeks back i was looking around the JavaScript sub Reddit and stumbled across this jQuery plugin, this plug in working with canvas to give the user a different experience when it comes to scrolling through web content. Instead of the normal downward scroll that almost all web pages have bar the rare horizontal scrolling pages (that everyone hates), this plugin makes the user go on a journey through the web pages taking endless moves as shown in the example i have provided.

&nbsp;

I was able to close the GitHub repo and install the demo and try it out. The code works by you designing your site with wrapper div that contains different stages of the path, each of these are div&#8217;s that can be used as way points e.g. start, middle end. Then in the JavaScript you can use a canvas like syntax to define the line or the path of the site e.g.

> .arc(200, 1200, 400, <a class="linkification-ext" title="Linkification: http://-Math.PI/2" href="http://-Math.PI/2">-Math.PI/2</a>, <a class="linkification-ext" title="Linkification: http://Math.PI/2" href="http://Math.PI/2">Math.PI/2</a>, true)

This will arc the line and then this can be linked to a way-point, for more examples checkout the <a title="Scroll Path GitHub" href="https://github.com/JoelBesada/scrollpath" target="_blank">GitHub</a> page for Scroll Path or check out my own <a title="Scroll Path Demo" href="../jQuery_Scroll_Path/" target="_blank">demo</a> taken from the GitHub page.