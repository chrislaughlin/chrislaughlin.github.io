---
layout: post
title: "SMACSS: Scalable and Modular Architecture for CSS"
date: "2015-07-19"
---

I have been working a lot recently with CSS and updating application styles.
I have always followed the simple pattern of placing all CSS in one file (stlye.css). However when I started started working with SASS I started to break up the styles into logical files, each file folding the styles for a page or a section of a page. This still ended led to issues are the file would grow and I would usually end up with reproduced styles and when it came to removing a style it was hard to trace.

## SMACSS
SMACSS is a style guide you can follow that will provide more organization for your css. Its promoted as not a framework but a way to examine your design process. SMACSS is broken up into a number of categories:
* Base
* Layout
* Module
* State
* Theme

Each of these categories can be used to structure the css of a project.

#### Base
Base styles are styles that will cover the whole project. Root document styles such as the body text, links styles and anything else that can cover the whole project.

```
body {
    margin: 0;
    padding: 0;
    font-family: "Bell MT", BellMT, Garamond, Georgia, “Times New Roman”, Times, serif;
    line-height: 1.5;
    color: #333;
}

a {
  color: #039;
}
```
We can see from the example above that we are setting the font for the document and also setting the links colors. Anything that is not specific to a part of the application can be added to your base.

#### Layout
Layout as you can guess takes responsibility for the layout of the document. The layout would contain the styles for blocks on the page such as a nav bar, header, main content area and a footer. The layout file could look something like:
```
nav {
  width: 20%;
  float: left;
},
main {
  width: 80%
  float: left;
}
footer {
  width: 100%
}
```
Here we can see the different sections of the application.

#### Modules
Modules are used to store the different parts of the application, If you page has blog posts on it and each post has a preview. This is a module you can contain the styles for that module in a file named preview.css. You can also extend modules and have submodules.

#### State
State rules are ways to describe a our module or layout will look when in a particular state. Is it hidden or expanded? Is it active or inactive? They are about describing how a module or layout looks on screens that are smaller or bigger. They are also about describing how a module might look in different views like the home page or the inside page.

#### Theme
Themes are simular to state in that the can describe how a part of the page looks. However different to state the theme can be used to change to look of the page based on a user preference.

### Why SMACSS
So you know what SMACSS can do for your css but why should you use it. When working on large scale JavaScript applications it is common to break up the code into manageable areas such as modules or use a MVC style structure. Why not apply the same to css, when multiple developers are working on code things can get messy. Merge conflicts, code duplication and complexity can and will happen unless some rules are introduced.

With SMACSS you can break down the css into manageable chunks and allow for developers to work together with little to no issues. 
