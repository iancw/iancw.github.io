---
layout: post
status: publish
published: true
title: Java Interview Questions
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 16
wordpress_url: http://iancwill.com/blog/?p=16
date: '2007-09-19 00:43:00 -0600'
date_gmt: '2007-09-19 00:43:00 -0600'
categories:
- Uncategorized
tags: []
comments: []
---
<p>As a team lead, I'll be participating in the interview process.  We've got an interview tomorrow, and I've been asked to prepare to spend some time with the candidate.  So what questions are good to ask when interviewing a Java developer?<br &#47;>
<ul><br &#47;>
<li>When is a finally block entered?<br &#47;>
<ul>
<li>After catching an exception?<&#47;li>
<li>After successful completion of the try block?<&#47;li>
<li>Will it be entered if the exception is not caught?<&#47;li>
<li>Will it be entered if the application exits?<&#47;li><&#47;ul><&#47;li>
<li>Can you pass by value in Java?<br &#47;><i>(Answer: primitives are passed by value, you could argue that references=pointers, and that the pointers are  <a href="http:&#47;&#47;javadude.com&#47;articles&#47;passbyvalue.htm">passed by value<&#47;a>)<&#47;i><&#47;li>
<li>Is there a difference between Hashtable and HashMap?<&#47;li>
<li>How about between Vector and ArrayList?<&#47;li>
<li>What's the difference between swing and awt?<br &#47;><i>(Answer: Light-weight vs heavy-weight) <&#47;i><br &#47;>
<ul>
<li>What's the difference between light and heavy weight components?<&#47;li><i>(Answer:  Light-weight = same appearance on all platforms, but slower execution)<br &#47;>(AWT components map to the OS's windowing toolkit, whereas swing is implemented with Java2d)<&#47;i><br &#47;>
<li>Are light and heavy weight components interchangable?<br &#47;><i>(Looking for knowledge that they shouldn't generally be used together due to z-buffer incompatabilities)<&#47;i><&#47;li>
<li>Is there a naming convention to distinguish heavy from lightweight components?<br &#47;><i>(the J-prefix...)<&#47;i><&#47;li><&#47;ul><&#47;li>
<li>What are the values of s1 and s2 after invoking the <i>swap<&#47;i> method?<br &#47;><br />
<blockquote>public void swap(String s1, String s2)<br &#47;>{<br &#47;>   String tmp = s1;<br &#47;>   s1 = s2;<br &#47;>   s2 = tmp;<br &#47;>}<br &#47;>String s1 = "a";<br &#47;>String s2 = "b";<br &#47;>swap(s1, s2);<br &#47;><&#47;blockquote><br &#47;>
<ul>
<li>What happens if primitive ints are used instead of Strings?<&#47;li>
<li>What happens if we make the arguments of the swap function final?<&#47;li><&#47;ul><&#47;li>
<li>Give an example of a method that can swap values of two variables with effects preserved in the caller's scope.<br &#47;><i>Example: <br &#47;><br />
<blockquote>public void swap(Point p1, Ptring p2)<br &#47;>{<br &#47;>   Point tmp = new Point(p1.x, p1.y);<br &#47;>   p1.x = p2x; p1.y = p2.y;<br &#47;>   p2.x = tmp.x; p2.y = tmp.y;<br &#47;>}<br &#47;><&#47;blockquote><&#47;i><&#47;li>
<li>What happens if we make the arguments to the working swap function <b>final<&#47;b>?<&#47;li><br &#47;><&#47;ul></p>
