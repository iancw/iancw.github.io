---
layout: post
status: publish
published: true
title: Your Developers Aren't Slow?
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 206
wordpress_url: http://iancwill.com/blog/?p=206
date: '2014-12-10 22:07:08 -0700'
date_gmt: '2014-12-11 03:07:08 -0700'
categories:
- Uncategorized
tags: []
comments: []
---
<p>A friend sent me a link to "<a href="https:&#47;&#47;sprint.ly&#47;blog&#47;your-developers-arent-slow&#47;">Your developers aren't slow<&#47;a>" today after I basically accused our dev team of being slow following an particularly unproductive sprint.</p>
<p>The article's points appear to be....</p>
<p> 1. Developers average pretty consistent start-to-complete rates<br />
 2. Speccing out and prioritizing work has more volatility than actual development<br />
 3. Time from done to deployed is significant</p>
<p>Therefore, it's likely there are other causes to slower than desired deployment rates than deficient developers.  They suggest things that slow down your deployment might include...</p>
<p> 1. Unclear requirements<br />
 2. Changing requirements<br />
 3. Context switching</p>
<p>Then they say managers should...</p>
<p> 1. Define a clear vision<br />
 2. Write well-designed user stories and bug reports<br />
 3. Reduce context switching</p>
<p>There's some redundancy there.  There seem to be two main suggestions.</p>
<p> 1. Write better work specifications<br />
 2. Prevent context switching</p>
<p>The first point is true of our team--many of our tickets are vague.  It's not uncommon for us to fundamentally change the design after a job has been completely finished once.  I have one in mind now--a UI element that I'm not happy with.  I wasn't involved in the design, and I'm technically not on the QA path, but I have major issues with the look and feel.  I would fail it and suggest a completely different UI design.  I guess that does slow us down in the long run.  Perhaps I should consider ways to track time lost due to post-mortem re-designs.  Every release cycle has at least a few features that we completely rework once or twice.  Some of that could be alleviated by better design up front.</p>
<p>But that wasn't the problem this sprint...for most of us.  Though as I write, I realize that poor specifications have significantly slowed one of our new developers.  He has basically had to teach himself the domain so he could design appropriate specifications himself.  That has cost him significant development time.</p>
<p>Context switching is another great thing to consider.  Joel Spolsky has some interesting thoughts on <a href="http:&#47;&#47;www.joelonsoftware.com&#47;articles&#47;fog0000000022.html">task switching<&#47;a>.  In a nutshell:  don't do it (as a programmer).  As a manager, don't let your programmers do it.  Programmers will naturally avoid context switching, so really that last sentence should read "don't force your programmers to task switch."  Context switching certainly contributed to some productivity problems last sprint, as our most senior developers were context-switched to non programming tasks much more than usual.  </p>
<p>There's another aspect of context switching that is annoying but seems inevitable--code reviews.  Our team has an ad-hoc review process.  When you finish development, just ask anyone else on the team to review your work.  However, our most talented developers are typically the ones asked to do the reviews.  They also have a vested interest in keeping the code base up to their standards.  But that can be a lot of context switching.  I spent almost half my day doing a code review (and rebasing a branch on the side).</p>
<p>Another interesting idea in Joel's article is the consideration of work latency.  If small tickets block on large tickets (or if they share the same person's time equally), the average completion time drops, even if the total number of completed tasks is equal.  If we want to decrease average task time, we should front-load the short tickets.  Of course, that's kind of gaming our metrics.  Ultimately what matters is total number of completed tickets per release.  And superseding raw counts is the goal of increasing product quality every release.  There might be other benefits from front-loading easy work.  It builds momentum.  After a few days of productive coding, it feels easier to continue being productive.  Seeing your work merged and feeling the accomplishment of completed work is satisfying and motivating.</p>
<p>I should look more critically through our tickets before our next sprint kick-off though, and make sure the details are specified sufficiently that developers don't have to go hunting and guessing, and that completed work doesn't need major overhauls.</p>
