---
title: Renaming your slash lib folder
author: chris
layout: post
permalink: /2011/06/15/renaming-your-slash-lib-folder-2/
blogger_author:
  - Chris Laughlin
blogger_blog:
  - limitedconnection.blogspot.com
blogger_permalink:
  - /2011/06/renaming-your-slash-lib-folder.html
categories:
  - Uncategorized
---
<div>
  <p>
    Well do I was working with the GDB cross compiler and needed to configure it by renaming the /usr/lib folder however in my haste I renamed the /lib folder. After doing this I retire what anyone would do and run mv /lib-old /lib but to my wonder there was no lib command and no other command line well comands ad they are all stored in /lib. <br />Luckly I was running on a VM and I was able to start up a different ubuntu machine mount the broken drive and rename the folder.
  </p>
  
  <p>
    The lesson I learnt here was if you have to Sudo the command then think twice.&#160;&#160;&#160;&#160;
  </p>
</div>