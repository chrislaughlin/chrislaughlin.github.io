---
layout: post
title: "JetBrains Intellij Workshop"
date: "2015-02-16"
---

Today I attended a workshop from the team at Jetbrains, the workshop gave a detailed look into the Intellij IDE. The workshop was presented by [Hadi Hariri](http://hadihariri.com/), with his anti mouse philosophy in mind we dug into the ways to using Intellij to work efficiently. I will outline some of the take away points that I felt that most developers would not know and must learn if you plan to use or already use Intellij to develop.

##Navigation

*"use the keyboard”* the mantra that Hadi repeated and which made me feel bad for all the times I’v used the mouse.

[Presentation assistant](https://plugins.jetbrains.com/plugin/7345?pr=idea) was shown at the point as Hadi would be using the keyboard to do everything we would need to see what key combinations were being executed. Presentation assistant flashes up on screen what keys are used to carry out an action and the action name. This will now be turned on anytime that I do live coding demos and you should do the same. This feature should also be turned on while you are pair programming for the times when you are bashing away on the keyboard and the other developer is lost to the world trying to work out what the you are doing.

So now on to the meat of the workshop the hip cool key combinations that will make you look **L33T** in front of all you programming friends.  

###Navigation:
- ```cmd + o``` get to class
- ```cmd + 1``` open the project structure  
  - In the project structure you can also:
    - start typing and this will search for the file
    - set auto scroll so that files opened via search are scrolled to on the project view
- ```shift (double press)``` search everywhere this will search not only classes but files, build tasks, features anything you can really think about.
In this feature you can also toggle IDE features
Run build configurations
- ```cmd + 7``` file structure of the project
- ```cmd + n``` create new file
  - in the new file selection you can also start typing to search/refine the selection
- ```cmd + e``` show recent file
  - this comes into play especially if you disable tabled editing, Hadi was an advocate of the one tab rule in which you only have one file open at as time and using the file navigation built into Intellij you can go back and forth. Tab settings can be changed from the general settings menu and any limit can be set on the number of open tabs.
- ```shift + cmd + e``` show recently edited files
- ```cmd + y``` show a popup window of the code definition
- ```cmd + b``` go to the code definition

###Windows
- ```shift + cmd F12``` hide all windows except the file you are editing

###Text
- ```alt + up``` select line (context aware) e.g. select var, then function the class etc
- ```shit cmd enter``` statement complete can be used to complete if statements

###Refactoring Code  
- [import preferences](https://www.jetbrains.com/idea/help/optimizing-imports.html) allows you to import a namespace or each individual class, you can also add tolerances to if more that say 3 classes are used from a package then you can import the package.
- ```cmd + t``` surround code, allowing you to surround a statement easily

These are just some of the tips and tricks that I had picked up from the workshop, the help documentation built into Intellij and the [web site](https://www.jetbrains.com/idea/help/intellij-idea.html) is a great resource for looking for shortcuts and different approaches for completing a task. 

If you have learnt any tips or tricks for using this very powerful IDE please leave a comment.
