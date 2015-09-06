---
layout: post
title: "CSS Flexbox"
date: "2015-09-06"
---

Flexbox is a CSS property that aims to provide a better method to page layout that the currently popular methods using floats. I recently came across Flexbox when working on  CSS bug. I preformed the usual Stackoverflow search and blindly copied and pasted the answer into my code. As expected everything work, but why? What was tis Flexbox I was seeing?  

I decided to look into Flexbox and here is a very basic overview of how to use Flexbox. Flexbox is an alternative was to control page layout, without the need for floats. Floats have there own advantages and disadvantages. The main idea behind Flexbox is the ability for the container element to dynamically alter the size of its child elements. This leans it use towards responsive design as it will work to fill the container area as best as possible. 

The example below shows a container div with 5 children, the container has flex as is display while the children all have flex:1 set.

<p data-height="257" data-theme-id="18619" data-slug-hash="ojXvBd" data-default-tab="result" data-user="chrislaughlin" class='codepen'>See the Pen <a href='http://codepen.io/chrislaughlin/pen/ojXvBd/'>ojXvBd</a> by Chris Laughlin (<a href='http://codepen.io/chrislaughlin'>@chrislaughlin</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Note that each child is of equal height and width and all work to fill the parent container. This is the power of Flexbox, there is no need to set any width or height of the container or the children. Also note that the flex:1 of the child is does not effect the layout. This will be applied to each child and will be come more clear in the next example.  

<p data-height="257" data-theme-id="18619" data-slug-hash="pjJzzv" data-default-tab="result" data-user="chrislaughlin" class='codepen'>See the Pen <a href='http://codepen.io/chrislaughlin/pen/pjJzzv/'>pjJzzv</a> by Chris Laughlin (<a href='http://codepen.io/chrislaughlin'>@chrislaughlin</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

You can see from the above example box 2 is bigger this is because we have set it with a higher flex than the others. So now box 2 is two times the size than the others. This can be done for any of the boxes just by changing the flex value. So on that thought you could potentially make a 3 column layout (that was all the rage back in the day) by setting the flex of the middle column and you get responsive design for free.

<p data-height="257" data-theme-id="18619" data-slug-hash="zvGOYN" data-default-tab="result" data-user="chrislaughlin" class='codepen'>See the Pen <a href='http://codepen.io/chrislaughlin/pen/zvGOYN/'>zvGOYN</a> by Chris Laughlin (<a href='http://codepen.io/chrislaughlin'>@chrislaughlin</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

## Browser Support
Now for the bad part, there is currently not full browser support for Flexbox, currently Chrome, Firefox, Safari, IE (11), Opera and Android (4.4.4+) have full support. Other browsers require you to add a prefix however if you are using SASS or LESS you could use a [mixin](https://github.com/mastastealth/sass-flex-mixin/blob/master/_flexbox.scss) to achieve this.  
