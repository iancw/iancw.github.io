---
layout: post
status: publish
published: true
title: Retrieving a phone contacts from Motorola V195
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 75
wordpress_url: http://iancwill.com/blog/?p=75
date: '2011-12-16 10:22:53 -0700'
date_gmt: '2011-12-16 15:22:53 -0700'
categories:
- Uncategorized
tags: []
comments: []
---
<p>I'm switching carriers, and my old phone was a motorola V195.  I want to get my phone contacts off, but there seems to be no good way to do it with my macs at home and free software.  I refuse to buy something for a one-time chore of moving contacts between phones.  The Wammu&#47;Gammu software might work on linux, but it didn't compile on a first attempt on my mac.</p>
<p>Enter AT commands, which I learned about in my embedded programming class last semester.  It was remarkably easy to get in to the v195!  </p>
<p>Step 1:  Set up a bluetooth connection to the phone.<br />
  Edit the serial ports, set up an RS-232 link.  I'm not sure what the service field does, but leaving it as a network gateway worked.  Change the name to something short and easy to type.</p>
<p><img src="http:&#47;&#47;iancwill.com&#47;blog&#47;wp-content&#47;uploads&#47;2011&#47;12&#47;bluetooth-setup.png"&#47;><br />
<img src="http:&#47;&#47;iancwill.com&#47;blog&#47;wp-content&#47;uploads&#47;2011&#47;12&#47;bluetooth-edit.png"&#47;><br />
<img src="http:&#47;&#47;iancwill.com&#47;blog&#47;wp-content&#47;uploads&#47;2011&#47;12&#47;bluetooth-serial.png"&#47;></p>
<p>Step 2:  Run mini com</p>
<p>Now you can connect to the serial port using minicom, start it with the -s flag to change configuration before trying to connect.</p>
<blockquote><p>minicom -s<&#47;blockquote><br />
<img src="http:&#47;&#47;iancwill.com&#47;blog&#47;wp-content&#47;uploads&#47;2011&#47;12&#47;minicom-config.png"&#47;></p>
<p>  Use baud 9600 with 8N1 and change the name of the serial device to &#47;dev&#47;tty.<what you typed in the name field></p>
<p>Step 3:  Go to town!<br />
  Test the connection by typing AT, you should see an OK back. </p>
<blockquote><p>
AT<br />
OK<br />
AT+CGMI<br />
+CGMI: "Motorola CE, Copyright 2000"<br />
OK<br />
AT+CGMM<br />
+CGMM: "GSM900","GSM1800","GSM1900","GSM850","MODEL=V195"<br />
OK<br />
<&#47;blockquote></p>
<p>There's a good description of motorola AT commands <a href="http:&#47;&#47;www.motorola.com&#47;web&#47;Business&#47;Products&#47;M2M%20Wireless%20Modules&#47;C24%20CDMA%20Wireless%20Module&#47;Document&#47;staticfile&#47;C24%20AT%20commands.pdf">here (pdf)<&#47;a>. For my purposes the AT+CPBR=# command is what I was looking for.  </p>
<blockquote><p>
OK<br />
AT+CPBR=1<br />
+CPBR: 1,"###########",129,"Mom"<br />
<&#47;blockquote><br />
The number defines which entry in the phone book you need.  Now I just need to write a program that pulls all these down automatically.</p>
