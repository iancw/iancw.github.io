---
layout: post
status: publish
published: true
title: Ghost => Github
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 154
wordpress_url: http://iancwill.com/blog/?p=154
date: '2013-12-25 20:41:47 -0700'
date_gmt: '2013-12-26 01:41:47 -0700'
categories:
- Uncategorized
tags: []
comments: []
---
<p>Ghost (<a href="https:&#47;&#47;ghost.org">https:&#47;&#47;ghost.org&#47;<&#47;a>) is a new blogging system that is exciting in its simplicity.  I've started using it to jot down my thought process while working through development problems.  No other note taking platform I've found lets you combine text, code snippets, and images in the same document with so little friction.  Also, the notes are easily shared with coworkers.  It helps that it looks beautiful out of the box.  I'm much more likely consistently use beautiful tools.</p>
<p>Furthermore, a Ghost blog can be easily re-published as a Github page.  I've set up mine on our internal Github Enterprise server so other members of my team can access my thought process.  I found a tiny python project called Buster (<a href="http:&#47;&#47;blog.axitkhurana.com&#47;introducing-buster&#47;">http:&#47;&#47;blog.axitkhurana.com&#47;introducing-buster&#47;<&#47;a>).  Buster is basically a wrapper around wget and git.  It calls</p>
<p><code><br />
wget --recursive --convert-links --page-requisites --no-parent --directory-prefix=static --no-host-directories http:&#47;&#47;localhost:2368<br />
<&#47;code><br />
and then lets you push those pages to an appropriately named github repository & branch.</p>
<p>At first I thought buster was incompatible with pages that have leading paths.  The generated index.html looked on the root folder for assets, e.g. &#47;assets&#47;css&#47;screen.css.  This would work with personal pages, which get their own username.github.io URL, but project pages are not situated at the root, but at github-server&#47;pages&#47;group&#47;project, so the resources have the wrong relative path.</p>
<p>But after looking through the issues pages on the buster Github repository, it appears that the <code>--convert-links<&#47;code> argument to wget was a recent addition which wasn't included in the buster version that I installed with pip.  This extra argument solved the absolute path problem.  In the end, as light as buster is, it seems like an unnecessary wrapper.  A simple shell script seems like an even easier solution to mirroring my ghost repository.</p>
<p><code><br />
cd ~&#47;src&#47;blog<br />
wget --recursive --convert-links --page-requisites --no-parent --no-host-directories http:&#47;&#47;localhost:2368<br />
git add -A<br />
git commit -m "updates"<br />
git push origin gh-pages<br />
<&#47;code><br />
(<a href="https:&#47;&#47;gist.github.com&#47;iancw&#47;8128684">gist<&#47;a>)</p>
