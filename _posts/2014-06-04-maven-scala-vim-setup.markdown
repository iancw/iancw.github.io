---
layout: post
status: publish
published: true
title: Maven &#47; Scala &#47; Vim Setup
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 175
wordpress_url: http://iancwill.com/blog/?p=175
date: '2014-06-04 22:47:00 -0600'
date_gmt: '2014-06-05 02:47:00 -0600'
categories:
- Uncategorized
tags: []
comments: []
---
<p>I'm looking to learn two things at once.  Scala and the CMU Sphinx library for speech to text.  My maven and vim chops get brushed up along the way.</p>
<p>To generate a scala maven project (nice!):</p>
<p>mvn archetype:generate</p>
<p>This enters interactive mode, the first step is to choose your archetype.  I chose org.scala-tools.archetypes:scala-archetype-simple (option 939), then chose version 1.3 and answered some other questions about project name and package.  This popped out a folder with a pom and a couple initial scala files &#47; tests.  Nice! </p>
<p>Step two is getting scala syntax highlighting on.  I have been using maximum awesome to manage my vim profile, so I added </p>
<p>Bundle 'derekwyatt&#47;vim-scala'</p>
<p>to the bottom of my maximum-awesome&#47;vimrc.bundles file and range :BundleInstall from inside of mvim.  It took me a little while to realize I needed to Apple-Quit MacVim instead of just closing all windows.  When I did that, mvim came back up with scala syntax properly highlighted.  Nice!</p>
<p>Now to learn scala.  But first, an application....</p>
<p>CMU Sphinx (http:&#47;&#47;cmusphinx.sourceforge.net&#47;wiki&#47;tutorialsphinx4) has some maven stuff.  I'll see if I can hook that into my scala maven project and use the java libraries in a cool new language.</p>
<p>My first attempt I get "peer not authenticated" which later turned into "ava.security.InvalidAlgorithmParameterException: the trustAnchors parameter must be non-empty."  How lame.  Installing some random Apple Java update fixed the issue (http:&#47;&#47;support.apple.com&#47;kb&#47;DL1572), thanks KiwiMartin from stack overflow! (https:&#47;&#47;stackoverflow.com&#47;questions&#47;6784463&#47;error-trustanchors-parameter-must-be-non-empty&#47;19680689#19680689).  After installing that, mvm compile downloads the jars from sonatype.</p>
<p>Nice!  I seem to be able to import classes from edu.cmu.sphinx.api.  Now to learn some scala (http:&#47;&#47;www.scala-lang.org&#47;docu&#47;files&#47;ScalaTutorial.pdf).  Here's what I'm rocking so far:  https:&#47;&#47;github.com&#47;iancw&#47;scala-sphinx.</p>
