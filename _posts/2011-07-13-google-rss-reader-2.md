---
title: Google RSS Reader
author: chris
layout: post
permalink: /2011/07/13/google-rss-reader-2/
blogger_author:
  - Chris Laughlin
blogger_blog:
  - limitedconnection.blogspot.com
blogger_permalink:
  - /2011/07/google-rss-reader.html
categories:
  - Uncategorized
---
<span class="Apple-style-span" style="font-family: Georgia, serif; font-size: 16px;">So not too long ago I decided that I would take a challenge of reading up on and implementing a Google API in any language I can. The first API I have taken on is the Google Feed API, this API allows you to retrieve and display entries from a RSS feed. When using this I created a test page using JavaScript. the main code needed for returning the feed data and displaying the entries.</span> <div style="font-family: Georgia, serif; font-size: 16px;">
</div>

<div style="font-family: Georgia, serif; font-size: 16px;">
  The first Step is to reference and load the Google API using the Google API URL that must be referenced in the head of the html page displaying the feed.
</div>

<div style="font-family: Georgia, serif; font-size: 16px;">
  The next step is to call the code for getting the feed data shown below:
</div>

<div style="font-family: Georgia, serif; font-size: 16px;">
  <blockquote>
    <span class="Apple-style-span" style="font-family: 'Times New Roman'; font-size: small;"></span> <pre style="white-space: pre-wrap; word-wrap: break-word;"><span class="Apple-style-span" style="font-family: 'Times New Roman'; font-size: small;">var rss = new google.feeds.Feed(url);</span></pre>
    
    <p>
      <span class="Apple-style-span" style="font-family: 'Times New Roman'; font-size: small;"></span> <pre style="white-space: pre-wrap; word-wrap: break-word;"><span class="Apple-style-span" style="font-family: 'Times New Roman'; font-size: small;">rss.load("call back funtion");</span></pre></blockquote> 
      
      <p>
        <span class="Apple-style-span" style="font-family: 'Times New Roman'; font-size: small;"></span> <pre style="white-space: pre-wrap; word-wrap: break-word;"></pre>
        
        <p>
          When loading the feed you must pass in a call back function this will be executed once the the feed data has been loaded. In the function the best method to extract the data is to loop though the feed entries and format this into html data that can be passed into a div on the html page. an example of this is shown below.
        </p></div> 
        
        <div style="font-family: Georgia, serif; font-size: 16px;">
        </div>
        
        <p>
          var container = document.getElementById(&#8220;feed&#8221;); <br />for (var i = 0; i < result.feed.entries.length; i++) { <div>
            &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;var entry = result.feed.entries[i];&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;var br = document.createElement(&#8220;br&#8221;);&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;var div = document.createElement(&#8220;div&#8221;);&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp; div.appendChild(document.createTextNode(entry.title));&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp; div.appendChild(br);&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp; div.appendChild(br);&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp; container.appendChild(div);&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp; container.appendChild(br);&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp; div = document.createElement(&#8220;div&#8221;);&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp; var content = entry.content.replace(/(< ([^>]+)>)/ig,&#8221;&#8221;);&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp;div.innerHTML = content;&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp;container.appendChild(div);&nbsp;
          </div>
          
          <div>
            &nbsp; &nbsp; &nbsp; &nbsp;container.appendChild(br);&nbsp;
          </div>
          
          <div>
            } <div style="font-family: Georgia, serif; font-size: 16px;">
            </div>
            
            <div style="font-family: Georgia, serif; font-size: 16px;">
              This all can be seen on the example&nbsp;<a href="http://christopherlaughlin.co.uk/GoogleAPITesting/feed/feedTest.html">page&nbsp;</a>and more information can be seen on the&nbsp;<a href="http://code.google.com/apis/feed/">Google API site</a>.
            </div>
            
            <div>
            </div>
          </div>