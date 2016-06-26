---
layout: post
status: publish
published: true
title: Oracle sqlplus &#47; instant client on Mac OS X Lion
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 108
wordpress_url: http://iancwill.com/blog/?p=108
date: '2012-02-10 09:17:36 -0700'
date_gmt: '2012-02-10 14:17:36 -0700'
categories:
- Uncategorized
tags: []
comments: []
---
<p>Summary:  The 64 bit client doesn't work on Mac OS X Lion, but the x86 version does. </p>
<ol>
<li>Download the x86 basic client and the x86 sqlplus client from <a href="http:&#47;&#47;www.oracle.com&#47;technetwork&#47;topics&#47;intel-macsoft-096467.html">http:&#47;&#47;www.oracle.com&#47;technetwork&#47;topics&#47;intel-macsoft-096467.html<&#47;a><&#47;li>
<li>Unzip both into the same directory<&#47;li>
<li>Set DYLD_LIBRARY_PATH and run sqlplus<&#47;li><br />
<&#47;ol></p>
<p>With 32 bit...</p>
<blockquote><p>
iMac:instantclient_10_2-basic-x86$ DYLD_LIBRARY_PATH=`pwd` .&#47;sqlplus </p>
<p>SQL*Plus: Release 10.2.0.4.0 - Production on Fri Feb 10 09:12:52 2012</p>
<p>Copyright (c) 1982, 2007, Oracle.  All Rights Reserved.</p>
<p>Enter user-name: ^C<br />
<&#47;blockquote></p>
<p>With 64 bit...</p>
<blockquote><p>
iMac:instantclient_10_2-basic-x86$ cd ..&#47;instantclient_10_2-basic-x64&#47;<br />
iMac:instantclient_10_2-basic-x64$ DYLD_LIBRARY_PATH=`pwd` .&#47;sqlplus<br />
Segmentation fault: 11<br />
iMac:instantclient_10_2-basic-x64$<br />
<&#47;blockquote></p>
