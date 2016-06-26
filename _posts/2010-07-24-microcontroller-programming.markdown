---
layout: post
status: publish
published: true
title: Microcontroller Programming
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 25
wordpress_url: http://iancwill.com/blog/?p=25
date: '2010-07-24 06:16:00 -0600'
date_gmt: '2010-07-24 06:16:00 -0600'
categories:
- Uncategorized
tags: []
comments: []
---
<p><img src="http:&#47;&#47;farm5.static.flickr.com&#47;4143&#47;4822604791_1365984132_m.jpg" &#47;><br &#47;><br &#47;>This is really exciting.  I'm following the introduction to microcontroller programming tutorial at http:&#47;&#47;www.sparkfun.com&#47;commerce&#47;tutorial_info.php?tutorials_id=93.  I wasn't sure I would be able to write code for it on linux.  Well it was about as easy as it could get.  And I've got a blinking LED.<br &#47;><br &#47;><br &#47;><br />
<blockquote>ian@julia:~&#47;sandbox&#47;avr$ avrdude -p atmega168 -P &#47;dev&#47;parport0 -c stk200    -U flash:w:blink_1MHz.hex<br &#47;><br &#47;>avrdude: AVR device initialized and ready to accept instructions<br &#47;><br &#47;>Reading | ################################################## | 100% 0.00s<br &#47;><br &#47;>avrdude: Device signature = 0x1e950f<br &#47;>avrdude: Expected signature for ATMEGA168 is 1E 94 06<br &#47;>Double check chip, or use -F to override this check.<br &#47;><br &#47;>avrdude done.  Thank you.<br &#47;><br &#47;>ian@julia:~&#47;sandbox&#47;avr$ avrdude -p atmega328P -P &#47;dev&#47;parport0 -c stk200    -U flash:w:blink_1MHz.hex<br &#47;><br &#47;>avrdude: AVR device initialized and ready to accept instructions<br &#47;><br &#47;>Reading | ################################################## | 100% 0.00s<br &#47;><br &#47;>avrdude: Device signature = 0x1e950f<br &#47;>avrdude: NOTE: FLASH memory has been specified, an erase cycle will be performed<br &#47;>To disable this feature, specify the -D option.<br &#47;>avrdude: erasing chip<br &#47;>avrdude: reading input file "blink_1MHz.hex"<br &#47;>avrdude: input file blink_1MHz.hex auto detected as Intel Hex<br &#47;>avrdude: writing flash (300 bytes):<br &#47;><br &#47;>Writing | ################################################## | 100% 0.14s<br &#47;><br &#47;>avrdude: 300 bytes of flash written<br &#47;>avrdude: verifying flash memory against blink_1MHz.hex:<br &#47;>avrdude: load data flash data from input file blink_1MHz.hex:<br &#47;>avrdude: input file blink_1MHz.hex auto detected as Intel Hex<br &#47;>avrdude: input file blink_1MHz.hex contains 300 bytes<br &#47;>avrdude: reading on-chip flash data:<br &#47;><br &#47;>Reading | ################################################## | 100% 0.13s<br &#47;><br &#47;>avrdude: verifying ...<br &#47;>avrdude: 300 bytes of flash verified<br &#47;><br &#47;>avrdude: safemode: Fuses OK<br &#47;><br &#47;>avrdude done.  Thank you.<br &#47;><br &#47;>ian@julia:~&#47;sandbox&#47;avr$ <br &#47;><&#47;blockquote><br clear="all" &#47;></p>
