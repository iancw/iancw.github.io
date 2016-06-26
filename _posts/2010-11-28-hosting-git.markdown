---
layout: post
status: publish
published: true
title: Hosting git
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 28
wordpress_url: http://iancwill.com/blog/?p=28
date: '2010-11-28 03:20:56 -0700'
date_gmt: '2010-11-28 03:20:56 -0700'
categories:
- Uncategorized
tags: []
comments: []
---
<p>I finally registered a domain name and bought hosting. &nbsp;What finally pushed me over the edge was being able to host group projects for school under some password protection (instead of publicly available access over github, which may present academic integrity issues). &nbsp;Project number one (after ditching the default page provided by hostmonster), was setting up a git repo.</p>
<p>Thankfully I found this helpful post&nbsp;<a href="http:&#47;&#47;www.mobiphil.com&#47;2010&#47;03&#47;git-on-shared-hosting-with-git-http-backend&#47;">http:&#47;&#47;www.mobiphil.com&#47;2010&#47;03&#47;git-on-shared-hosting-with-git-http-backend&#47;<&#47;a> and this helpful precursor <a href="http:&#47;&#47;hostmonsterforum.com&#47;showthread.php?4589-HOWTO-install-Git-on-Hostmonster">http:&#47;&#47;hostmonsterforum.com&#47;showthread.php?4589-HOWTO-install-Git-on-Hostmonster<&#47;a>.</p>
<p>The only hangups I had were using the $HOME variable in git-http-backend.sh. &nbsp;It didn't work for me, but when I put the full path to my home directory everything started working fine. &nbsp;Even push!</p>
<p>But I'm having second thoughts about using git. &nbsp;Support on windows isn't too great. &nbsp;Maybe hg! &nbsp;They have a good tutorial too...</p>
