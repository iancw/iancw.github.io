---
layout: post
status: publish
published: true
title: Thoughts on Peopleware
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 145
wordpress_url: http://iancwill.com/blog/?p=145
date: '2013-12-23 22:41:13 -0700'
date_gmt: '2013-12-24 03:41:13 -0700'
categories:
- Uncategorized
tags: []
comments: []
---
<p>I've just been reading Peopleware, and have finished part 1 (Managing the Human Resource, chapters 1-6). This blog seems like as good a place as any to reflect.</p>
<h3>A few ideas I completely agree with<&#47;h3><br />
1. Many software development problems are social in nature<br />
2. People like to think their work is "high tech" when in reality most software work involves technical challenges with well-known solutions<br />
3. The stick (which the author labels "Spanish style management") is not an effective motivator</p>
<h3>New or interesting ideas<&#47;h3></p>
<p>1. Everyone wants to do high quality work.  Forcing low-quality work (usually via unrealistic schedules) inhibits motivation and can actually slow progress. Thus by managing in such a way as to trade quality for schedule, you actually lose both. However, boldly embracing quality-at-all-costs is scary.</p>
<p><em>"Quality is free, but only to those who are willing to pay heavily for it."<&#47;em></p>
<p>This is reminiscent of Christ's admonition in Matthew 16:25 <em>"For whoever would save his life will lose it, but whoever loses his life for my sake will find it."<&#47;em>. Though the principle pertaining to software quality is far less dire than when pertaining to one's soul.</p>
<p>But both arguments turn on the idea of commitment. Commitment to the value of quality is necessary to reap the benefits. Those benefits in a software group are not only quality, but also motivation, morale, and productivity.</p>
<p>2. The authors also dispel the principle known as <em>Parkinson's Law<&#47;em>, that is <em>"work expands to fill the time allocated for it."<&#47;em> If someone enjoys their work, they won't be inclined to let it drag on. Completing a project and shipping code is intrinsically satisfying. When someone has a habit of avoiding work, the authors suggest a few more likely causes than Parkinson's Law:</p>
<p>1. Lack of competency<br />
2. Lack of confidence<br />
3. Lack of affiliation with team members and project goals</p>
<p>They do however offer a corollary: <em>"Organizational busy work tends to expand to fill the working day."<&#47;em></p>
<p>They also highlight a study comparing performance with various estimates. When performing against a personally assigned time estimate, developers perform slightly better than against an estimate set by their boss. They perform significantly better against a time estimate set by a third-party analyst. But they are counter intuitively most productive when no time limit is set.</p>
<p>One can reason that unrealistic estimates can be demoralizing so that when there is no hope of achieving the goal there is little motivation (and perhaps some technical-debt accrued). A third-party analyst's estimate is probably more accurate given more experience estimating and more objectivity.</p>
<h3>Application<&#47;h3></p>
<p>While I look forward to subsequent segments of the book, there are a few shifts in mindset that I should make in response to the first few chapters.  I should see productivity mostly as a product of healthy motivation and confidence.  Thus when coworkers seem to be underperforming, my attempts at troubleshooting should look toward motivation.  It seems only fair to assume that all of my coworkers are equally desirous of doing high-quality work.  I should realize, however, that others' definitions of quality may differ drastically from my own.  Perhaps a group discussion of our individual perceptions of quality is in order.</p>
<p>Our team has bit of an over-loading problem.  We have a few more interesting projects than we have people to do them.  I also believe we have a productivity problem.  Although we operate (as I write I realize somewhat oxymoronically) without any real estimates or deadlines (which the authors say is theoretically the most productive environment).  It seems that the simplest projects can drag on for no discernible reason (...second corollary:  <em>"Uninteresting work expands to fill allotted time<&#47;em>"...).</p>
<p>There are actually a number of factors affecting my team's productivity.  I'll wager stabs at them in hopes of being proven right as I read on.  One is probably being prevented from working to personal quality standards.  We have developed a fairly heavy-handed code review culture.  We have strict styles and many subjective design guidelines.  I haven't championed these, but I have upheld and encouraged the group to hold to the strongest opinions.  I often fail code reviews for purely subjective design reasons.  Subjective criteria cause me to hesitate before asking for adjustments, but over time I've come to believe that fighting for simpler designs is a worthwhile battle.  But I think this discourages others and makes them feel less shared-ownership over our codebase.  So there is some tension over quality, and likely differing definitions.  </p>
<p>The idea of affiliation is also interesting.  My own personal motivation is significantly derived from affiliation with our product.  I think it's very interesting, I use it semi-regularly, I've had season where I've used it almost constantly, and I would like to see wider adoption.  Also, I understand pretty much everything it does, and have opinions about how those things could be improved.  Most other developers don't use the product for anything other than testing, and most haven't had to help others use it.  Perhaps this lack of affiliation for the end product also limits motivation?</p>
<p>Finally, we have a <em>Legacy<&#47;em> code base in all senses.  The age of a particular class can be deciphered like geologic strata by dating the fossilized design patterns.  The code base is difficult to learn and navigate, and almost any section of code has latent bugs waiting to be unearthed.  That technical debt is certainly also to blame for some of our lacking productivity.</p>
<h3>Action Summary<&#47;h3><br />
1. We should talk about definitions of quality as a group<br />
2. We should limit amount of work we accept to what we find interesting, and what we can accomplish without cutting corners</p>
