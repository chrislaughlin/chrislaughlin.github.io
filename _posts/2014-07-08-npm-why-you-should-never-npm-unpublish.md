---
title: 'NPM: Why You Should Never &#8220;npm-unpublish&#8221;'
author: chris
layout: post
permalink: /2014/07/08/npm-why-you-should-never-npm-unpublish/
dsq_thread_id:
  - 2852059873
categories:
  - applications
  - javascript
tags:
  - gulp
  - javascript
  - node
  - npm
  - package
---
<span id="1-293" class="white bg-black" style="color: rgb(0, 0, 0);">&#8220;npm</span><span id="1-294" style="color: rgb(0, 0, 0);"> </span><span id="1-295" class="red bg-black" style="color: rgb(0, 0, 0);">ERR!</span><span id="1-296" class="magenta"><span style="color: #000000;"> TypeError: Cannot read property &#8216;latest&#8217; of undefined&#8221;</span></p> <p>
  </span><span id="1-296">My build is failing on Travis CI but not locally, what is going on? This is what I was thinking last night after working on a feature for </span><span id="1-296"><a title="Time Booker Github" href="https://github.com/cam-technologies/time-booker" target="_blank">Time Booker</a> making a pull request and watching the build fail. I had a quick Google search and found some people talking about npm packages not downloading correctly so I decided to kick off the build again. </span>
</p>

<p>
  Failure again!  The same message but still no more details on what happened, we do have a pre-commit hook that will run everything except the production release task. I did not want to run this locally as it is very much built around being run on a Travis CI box. At this point it was getting late and I passed it off to the team to have a look at, thankfully we have an off shore member who is 9 hours ahead and was able to look at the issue while I slept.
</p>

<p>
  It turns out that one of the gulp packages we use (<a href="https://github.com/tomchentw-deprecated/gulp-conventional-changelog/issues/1" target="_blank">gulp-conventional-changelog</a>) had been removed from the npm repository. So why did this not fail on my pre-commit task? why did it fail on Travis? If you develop with node you will most likely run &#8220;npm install&#8221; on a fresh checkout of a project and after this always run &#8220;npm install some-random-package&#8221;. This is where the issue comes from, since I ran npm install when the change log package was in the repository it was downloaded to my npm modules folder and I never thought about it again. However when the build runs on Travis it will always clean up beforehand so the packages will always be downloaded as if it was a first time install and since the install is run with the quite param it would not give details on which package failed.
</p>

<p>
  If you were not to throw away your local modules folder and npm install you would never get the error. This brings many solutions into play:
</p>

<ul>
  <li>
    Set up and use your own node repository <ul>
      <li>
        This would prevent the error and allow for offline deployments however you would never know if a package was removed (and this is usually is for a good reason)
      </li>
    </ul>
  </li>
  
  <li>
    Clean your local node modules folder every time you push to your remote repository <ul>
      <li>
        This can take up a lot of time and is not maintainable
      </li>
    </ul>
  </li>
  
  <li>
    Force developers to not remove the package is there are any downloads from the main repository <ul>
      <li>
        This seems to be the best way and <a title="npm-unpublish" href="https://www.npmjs.org/doc/cli/npm-unpublish.html" target="_blank">recommended by npm</a>
      </li>
    </ul>
  </li>
</ul>

<p>
  The good people at npm recommend using <a title="npm-deprecate" href="https://www.npmjs.org/doc/cli/npm-deprecate.html" target="_blank">npm-deprecate</a> instead this will show a message to the user that they should stop using the package and hopefully recommend a new package or work around. Another advantage of the method is to support old project code. I have worked on many projects that use old libraries that have either gone out of support/development but there is no advantage of changing this so the project needs this library to be available for re-download etc.
</p>

<p>
  So the take-way from from this is always deprecate the package or people will cry!  One suggestion I have is only allow admins of the npm repository to remove packages and allow developers to only deprecate the package (but this could break down the community spirit of npm).
</p>