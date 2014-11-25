---
title: React JS Contact Card
author: chris
layout: post
permalink: /2014/08/10/react-js-contact-card/
dsq_thread_id:
  - 2916053700
categories:
  - applications
  - apps
  - javascript
tags:
  - angularjs
  - codepen
  - development
  - emberjs
  - facebook
  - github
  - javascript
  - reactjs
  - twitter
---
I recently attended a talk/master class on <a href="http://facebook.github.io/react/" target="_blank">ReactJS</a> given by <a href="https://twitter.com/kouphax" target="_blank">James Hughes</a> which covered the basics of the JavaScript framework including where it came from and how it works. I had seen some posts on reddit talking about React before but never really seen examples in the wild.

React was developed by Facebook it is a component based framework that focuses on the UI. Its promoted as the V in the MVC stack as React can be easily dropped into existing application. The logic behind React is the &#8220;virtual DOM&#8221; this enables React to update the UI in a one way reactive data flow. This provides a very different approach to the common two-way binding found many other JavaScript frameworks like <a title="Angular JS" href="https://angularjs.org/" target="_blank">Angular</a> and <a title="Ember JS" href="http://emberjs.com/" target="_blank">Ember</a>. The virtual DOM allows React to only update parts of the DOM that need changed, thus reducing the overhead of DOM manipulation. React components can be written in JavaScript or in JSX which compiles at build time to JavaScript. Facebook and Instagram use React for live components which show the technology can stand strong in the world of production code.

React has a flat learning curve, as if you already know JavaScript you can just jump right into React. The only struggle is getting you head around the life cycle of a component and how to achieve reactiveness with the single way binding.

After attending the talk and talking to a developer <a title="TWAT!!" href="https://twitter.com/madole" target="_blank">friend</a> we disagreed on the best approach to writing a React component; use JSX or JavaScript. I have never been a fan of languages that compile into JavaScript, I feel that it can sometimes over complicate an already tricky language. I also hate having to learn new syntax&#8217;s as I know too many already. To be fair there might be some advantages but I&#8217;m going to stick with my guns and go pure JavaScript.

We decided that we would both build a contact card in React and compare the code for readability, maintainability and over all look and feel. The min requirements were as follows:

*   Must take take data from json
*   Must present an avatar image
*   Must show name and tag line
*   Must have links to user sites: 
    *    Github
    *   Facebook
    *   Linkedin
    *   Twitter
    *   CV
    *   Blog ** the last two I added when building as they felt needed

After a few hours of mocking out what the card would look like I settled with the below design, I&#8217;m not an artist or a web designer so it&#8217;s not the best looking.

[<img class="aligncenter size-medium wp-image-1836" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/08/Screen-Shot-2014-08-10-at-17.54.19-400x260.png" alt="Screen Shot 2014-08-10 at 17.54.19" width="400" height="260" />][1]

Once I got the design down I started working from the smallest component up, trying to keep the card as extendable as possible I decided to break it up into a number of components. I started with the links these could be reused and would need data to be passed in so that the icon and link URI would be set. Below is the code for the link component.  
  
The link component will be called with the source (link URI) and the type facebook, github etc. I can then call this multiple times for the links that are rendered. This is the only component that houses any logic the others are more or less just printing elements with the data from the JSON. I Found the code to be easy to work with and actually fun to build with as it only took an hour to write.  I will hopefully be expanding the code and building more advanced components that expose the React stack.

You can find the full code for the contact card on <a title="Code Pen" href="http://codepen.io/chrislaughlin/pen/veEdI" target="_blank">CodePen</a>, you can also find loads more of examples on the React site and this really useful <a title="5 Practical Examples for React JS " href="http://tutorialzine.com/2014/07/5-practical-examples-for-learning-facebooks-react-framework/" target="_blank">tutorial</a>.

 [1]: http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/08/Screen-Shot-2014-08-10-at-17.54.19.png