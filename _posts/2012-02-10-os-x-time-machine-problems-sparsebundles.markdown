---
layout: post
status: publish
published: true
title: OS X, time machine problems, sparsebundles
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 70
wordpress_url: http://iancwill.com/blog/?p=70
date: '2012-02-10 09:04:06 -0700'
date_gmt: '2012-02-10 14:04:06 -0700'
categories:
- Uncategorized
tags: []
comments: []
---
<p>I got an iMac.  It's got a big, beautiful monitor and cool gestures.  Everything works mostly.  I formatted my Drobo to HFS+ awhile back and intend to plunge into the mac world full force.  I want to back up my macbook pro to the Drobo, but I want the Drobo always connected to the iMac.  Time machine does not officially support this.</p>
<p>I play around and learn that all my old macbook pro backups to the plugged-in Drobo can't be built on, since wireless backups use a sparse bundle scheme instead of a folder based filesystem.  I think the sparse bundles let it backup in small (apparently 8 MB) chunks or something.  It takes awhile for the shared drive to become visible to the macbook, but eventually things begin backing up after much rebooting, ejecting, and re-sharing.</p>
<p>Later, I close my macbook lid while it's backing up.  (It feels like it's always backing up.)  Then backups stop working.  It says &#47;Volumes&#47;Drobo&#47;vicious.sparsebundle is already in use or something.</p>
<p>Eventually I find this http:&#47;&#47;blog.jthon.com&#47;?p=31, which is the most helpful post so far.  I'm unable to attach with hdiutil, however, and it tells me "Resource temporarily unavailable."  Thankfully a commenter on Jthon's blog suggested to simply eject the drive.  OS X complained that the drive was shared and busy and I couldn't eject it, but</p>
<blockquote><p>hdiutil eject -force &#47;Volumes&#47;Drobo<&#47;blockquote> did the trick.  After I re mounted it (<br />
<blockquote>hdiutil attach &#47;Volumes&#47;Drobo<&#47;blockquote>), I was able to hdiutil -attach the drive.  However, in my case fsck_hfs -rf did not do the trick.  I got</p>
<blockquote><p>
iMac:blog will$ fsck_hfs -rf &#47;dev&#47;disk2s2<br />
** &#47;dev&#47;rdisk2s2<br />
   Executing fsck_hfs (version diskdev_cmds-540.1~34).<br />
   Invalid content in journal<br />
** Checking Journaled HFS Plus volume.<br />
   Invalid B-tree node size<br />
(3, 0)<br />
** The volume   could not be verified completely.<br />
   Invalid content in journal<br />
(3, 0)<br />
<&#47;blockquote></p>
<p>Now, however, my macbook doesn't see Drobo, and time machine thinks it needs to back up to Drobo-1.  How annoying.</p>
