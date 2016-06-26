---
layout: post
status: publish
published: true
title: Javascript?
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 186
wordpress_url: http://iancwill.com/blog/?p=186
date: '2014-09-10 22:43:59 -0600'
date_gmt: '2014-09-11 02:43:59 -0600'
categories:
- Uncategorized
tags: []
comments: []
---
<h2>Intro<&#47;h2><br />
Javascript was the first language I dabbled in.  Mostly that involved hooking into onClick events and change the colors of various websites I was building.  If only I could track down internet archives of those free geocities and angle fire sites...  Anyway, I went to school, learned Java, started getting paid to write Java, learned some ruby (thanks to Why's poignant inspiration), went back to school, learned some python, learned some rails, and started hacking together some javascript since that's the lingua-franca of the web.  I wrote some javascript hacks to put various cool things on small website projects (https:&#47;&#47;github.com&#47;iancw&#47;bus-tracker), (https:&#47;&#47;github.com&#47;iancw&#47;uview), (https:&#47;&#47;github.com&#47;iancw&#47;mountain-weather).  At some point, the project starts to get bogged down with disorganization.  In small projects, you can get by without much organization.  But as it grows larger and cooler and you start to want to do more with it, you hit a productivity wall.  Bus tracker (https:&#47;&#47;github.com&#47;iancw&#47;bus-tracker) &#47; (http:&#47;&#47;bus-tracker.herokuapp.com) is at this point.  It's got a bit of javascript spaghetti code, that squeaks its way through the rails asset pipeline, uses liberal global variables (some of which are inserted in the rails layout...), has zero unit tests, but got the job done for our class assignment.</p>
<p>Now that I'm picking it back up and using it as a playground for experimenting with <a href="https:&#47;&#47;www.mapbox.com" title="map box">mapbox<&#47;a>, it seems like a good time to understand Javascript.  I understand how to write a function, and even make an AJAX call, but I have little clue about turning out a sane codebase in javascript.  Testing?  Encapsulation?  Are these possible?  Also, what are the buzzwords and frameworks...node.js, angular.js, jquery...what are the cool kids doing in the javascript world these days?</p>
<p>The next few blog posts will be my notes and thoughts as I try to come up to speed on the state of Javascript. </p>
<h2>Node.js<&#47;h2><br />
It's a runtime.  Built on chrome's javascript engine.  It was created in 2009.  it has a package manager:  npm.  It's server-side javascript.  Not client side seemingly.  Everyone's making a big deal about it's non-blocking I&#47;O.  It sounds like it shines in highly interactive, websites; a replacement for flash and applets.</p>
<p>Resources to follow up on:</p>
<p> - http:&#47;&#47;www.toptal.com&#47;nodejs&#47;why-the-hell-would-i-use-node-js<br />
 - http:&#47;&#47;www.toptal.com&#47;javascript&#47;guide-to-full-stack-javascript-initjs</p>
