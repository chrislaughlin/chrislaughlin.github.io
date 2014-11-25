---
title: 'Web Storm: Live Templates'
author: chris
layout: post
permalink: /2014/11/16/web-storm-live-templates/
dsq_thread_id:
  - 3230596671
categories:
  - applications
  - development
  - javascript
tags:
  - idea
  - javascript
  - webstrom
---
After reading through a recent Reddit post on popular JavaScript IDE&#8217;s, I discovered a hidden gem in the Jet Brains
IDE range (Intellij, Web Storm etc). Live templates provide a way of adding key shortcuts for common code snippets,
allowing you to assign abbreviations to code snippets and even have template variables.  You can access the live templates
by going to settings and searching for &#8220;Live Templates&#8221; you will see a list of the current templates. On this
screen you will be able to add new templates, below are a few examples that I have added.

### For Loop
{% highlight javascript %}
**
 * @abbr: for
 * @desc: for loop
 * @param $INDEX$ {jsSuggestIndexName()} [i]
 * @param: $ARRAY$ {jsArrayVariable()} [array]
 * @param: $VAR$ {decapitalize(jsArrayVariable())} [a]
 */
for (var $INDEX$ = 0, len = $ARRAY$.length; $INDEX$ < len; $INDEX$++) {
    var $VAR$ = $ARRAY$[$INDEX$];
    $END$
}
{% endhighlight %}

### Console Log
{% highlight javascript %}
/**
 * @abbr: clog
 * @desc: console log
 */
console.log($END$);
{% endhighlight %}

<a href="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/11/consoleLog.gif"><img class="size-full wp-image-1877 aligncenter" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/11/consoleLog.gif" alt="switch" width="371" height="237" /></a>

### Switch
{% highlight javascript %}
/**
* @abbr: sw
* @desc: switch statement
* @param: $condition$
* @parm: $case$
**/
switch ($condition$) {
    case $case$:
        break;
    $END$
};
{% endhighlight %}

<a href="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/11/switch.gif"><img class="size-full wp-image-1877 aligncenter" src="http://www.christopherlaughlin.co.uk/wp-content/uploads/2014/11/switch.gif" alt="switch" width="371" height="237" /></a>

You can find a large list of useful templates <a href="https://gist.github.com/ngryman/4760153" target="_blank">here</a>.