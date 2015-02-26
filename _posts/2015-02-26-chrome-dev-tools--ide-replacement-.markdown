---
layout: post
title: "Chrome Dev Tools - IDE Replacement "
date: "2015-02-26"
---
I recently talked at locally [JavaScript meetup](http://twitter.com/belfastjs) I talked about the top 5 features of the Chrome developer tools. I have given a simular talk at my old company which talked through the dev tools and how they can be used to improve the development process.

After the first talk it started to dawn on me that with some of the features in the tool kit you could get to the point of replacing the development IDE. The development cycle can be a comfortable or painful process for a developer, I have worked on some projects where the time between making a code change and seeing the results could take up to 5 minutes.

So how do we streamline this process, enter [Chrome developer tools](https://developer.chrome.com/devtools). The most powerful feature in the sources pannel.

![Chrome Source Panel]({{ site.url }}/assets/sources-pannel.jpg)

As the complexity of JavaScript applications increase, developers need powerful debugging tools to help quickly discover the cause of an issue and fix it efficiently. The Chrome DevTools include a number of useful tools to help make debugging JavaScript less painful.

The sources panel provides all the needed tools for developing;
- breakpoints
- call stack
- watches
- console execution
- live editing of code

This is all great but we are still only in the dev tools, we still need a IDE or text editor to create the code then open it in chrome. What if we could edit the code and not have return the to IDE to make the changes again.

Well we can, dev tools allows you to map files to a local workspace. This makes a link between the files in the browser to the files on you local machine. See this in action below:

![Adding a workspace](http://g.recordit.co/5ST36xVg3B.gif)

Now that the workspace is linked you can make changes in the browser and have these saved to the local file, this now breaks the link between the IDE and the browser. You have created a instant feadback loop.

This shows the power of the Chrome developer tools, this is only the start. As time progresses the dev tools will grow it's feature set providing more options for developers. If you have any cool tips or tricks for the dev tools please leave a comment. 
