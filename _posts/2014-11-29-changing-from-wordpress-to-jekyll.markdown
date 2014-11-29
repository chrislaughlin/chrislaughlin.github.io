---
layout: post
title: "Changing from Wordpress to Jekyll"
date: "2014-11-29"
---
## Changing from WordPress to Jekyll

It has been a long time coming but I finally made the jump and moved to Jekyll. Since attending a local tech talk with a few people mentioning Jekyll and Github pages I been looking to try it myself.

### The Why

For the last few years I have been running a Wordpress blog hosting content ranging from photography to programming. This was manageable and allowed me to serve the content I needed. However I did run into some issues:

- Finding a free and easy to use image gallery was not easy
- Managing plugins became a chore
- Page speed was becoming a blocker for using the site, with some pages taking 1+ minutes to load

### The How

I decided for starters I would use my Github account to [host](https://pages.github.com/) the new Jekyll site. The fact that the hosting is free and managed though git really attracted me towards this approach. I followed the standard setup process from the [Jekyll site](http://jekyllrb.com/) which was painless.

{% highlight bash %}
gem install jekyll
jekyll new my-awesome-site
cd my-awesome-site
{% endhighlight %}

The next step was to try and import my exiting wordpress bog into Jekyll, this is where it all went down hill. It seems that the standard process is to export your wordpress content to a xml file then process this with the Jekyll importer. This repeatedly gave me errors with what I can only think of as missing gem files that were required for the import. As Im not a big user of ruby  I was unable to dig into this deeper but I think this might have been related to the issues of multiple versions of ruby installed OSX.

I ended up using a wordpress plugin '[Export Jekyll](https://github.com/benbalter/wordpress-to-jekyll-exporter)' which can export the content post, pages and images in a Jekyll friendly format. Each wordpress post would be converted to a markdown file and have the correct syntax, this also had some problems. When first trying to export I repeatedly got errors from my web host complaining that the temp folder was running out of space. I gathered from this that the export plugin was using the ```/temp``` folder to generate the contect then deliver a download file. Without access to change the size of my /temp folder I decided to clean out the large files in the wordpress content folders. The export then worked I was able to simply drop the new markdown files into the ```_post``` folder and I was migrated (though there was some tweaking of the existing posts).
