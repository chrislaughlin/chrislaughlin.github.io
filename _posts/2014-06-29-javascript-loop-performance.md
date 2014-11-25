---
title: JavaScript Loop Performance
author: chris
layout: post
permalink: /2014/06/29/javascript-loop-performance/
dsq_thread_id:
  - 2852046955
categories:
  - development
  - javascript
tags:
  - for
  - javascr
  - loop
  - Performance
---
I recently had a Google hangout with my team at CAM Tech, we got chatting about other work we had been bogged down with and one team member mentioned that he was working on JavaScript performance work &#8220;removing all the for in loops&#8221;. I had mentioned that a reverse while loop usually gives you the best performance however he countered with a standard for loop with a pre increment (++i). All of this got me thinking about loop performance as i had taken this task on recently before and though I would do some experiments.

To start off I would look at the standard for loop with i++ and compare with ++i.

## For Loops

Running the above code returns the following times: loop ++i: 0.040ms loop i++: 0.024ms loop length var: 0.029ms loop reverse: 0.016ms So from the results we can see that the quickest loop was the reverse loop. So from looking around and doing some reading its not the act of looping in reverse its the fact that the index (i) is defined as the length of the array which takes away the need for checking the length of the array on each iteration. However this could not be completely true as we can see that the loop length var also sets the length variable so that its not looked up on every iteration. It could be the cost of addition is more that subtraction, time for more tests I think.  
So after running the above and getting some strange results, I had to run each 5 times to get an average and it was clear that subtraction was quicker with an average of 25.4 ms while addition had an average of 27ms. This might explain the loop performance its not just the fact that the length is not being calculated each time but that the action of subtraction is being used.

&nbsp;

## Take Aways

So from the examples we can see that if you want your loop to be as fast as possible then cache the length and iterate backwards through the loop. However not all scenarios can handle the backwards iteration as some loops need a order to be maintained.  Some other interesting reading and test can be found behind the following links.

<a href="http://stackoverflow.com/questions/1340589/javascript-are-loops-really-faster-in-reverse" target="_blank">Are reverse loops really faster Stackoverflow</a>

<a href="http://jsperf.com/firstlooptest/6" target="_blank">Loop Test</a>

&nbsp;