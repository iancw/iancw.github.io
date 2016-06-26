---
layout: post
status: publish
published: true
title: Ruby, Gruff, Rmagic, imagemagick, ghostscripts, fonts, ARG!!!!
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 181
wordpress_url: http://iancwill.com/blog/?p=181
date: '2014-07-26 15:33:48 -0600'
date_gmt: '2014-07-26 19:33:48 -0600'
categories:
- Uncategorized
tags: []
comments: []
---
<p>I'm just trying to graph some bank balance history with ruby, because apparently all personal finances apps for OSX suck.  Ruby is way nicer than python, although it doesn't have numpy.  But numpy arrays aren't as great with heterogenous data, so I'd have to loop through it all anyway.  So why not use ruby, surely I can make a line graph easily?</p>
<p>Theoretically gruff solves the problem, if you can get rmagick installed right.  </p>
<blockquote><p>gem install rmagick<&#47;blockquote></p>
<p>All is well.</p>
<p>But when I run my program...</p>
<blockquote><p>iMac:simple-banking$ ruby quick-test.rb<br />
&#47;usr&#47;local&#47;Cellar&#47;ruby&#47;2.1.0&#47;lib&#47;ruby&#47;gems&#47;2.1.0&#47;gems&#47;gruff-0.5.1&#47;lib&#47;gruff&#47;base.rb:1142:in `annotate': unable to read font `&#47;usr&#47;local&#47;share&#47;ghostscript&#47;fonts&#47;n019003l.pfb' @ error&#47;annotate.c&#47;RenderFreetype&#47;1126: `(null)' (Magick::ImageMagickError)<br />
	from &#47;usr&#47;local&#47;Cellar&#47;ruby&#47;2.1.0&#47;lib&#47;ruby&#47;gems&#47;2.1.0&#47;gems&#47;gruff-0.5.1&#47;lib&#47;gruff&#47;base.rb:1142:in `annotate_scaled'<br />
	from &#47;usr&#47;local&#47;Cellar&#47;ruby&#47;2.1.0&#47;lib&#47;ruby&#47;gems&#47;2.1.0&#47;gems&#47;gruff-0.5.1&#47;lib&#47;gruff&#47;base.rb:888:in `draw_no_data'<br />
	from &#47;usr&#47;local&#47;Cellar&#47;ruby&#47;2.1.0&#47;lib&#47;ruby&#47;gems&#47;2.1.0&#47;gems&#47;gruff-0.5.1&#47;lib&#47;gruff&#47;base.rb:445:in `draw'<br />
	from &#47;usr&#47;local&#47;Cellar&#47;ruby&#47;2.1.0&#47;lib&#47;ruby&#47;gems&#47;2.1.0&#47;gems&#47;gruff-0.5.1&#47;lib&#47;gruff&#47;line.rb:174:in `draw'<br />
	from &#47;usr&#47;local&#47;Cellar&#47;ruby&#47;2.1.0&#47;lib&#47;ruby&#47;gems&#47;2.1.0&#47;gems&#47;gruff-0.5.1&#47;lib&#47;gruff&#47;base.rb:424:in `write'<br />
	from &#47;Users&#47;will&#47;src&#47;simple-banking&#47;play.rb:46:in `graph_balance'<br />
	from quick-test.rb:4:in `<main>'<br />
^C<br />
<&#47;blockquote></p>
<p>These guys propose a solution: http:&#47;&#47;rubyjunction.us&#47;issues-with-imagemagick----unable-to-read-font, who references https:&#47;&#47;garrickvanburen.com&#47;archive&#47;installing-imagemagick-rmagick-on-os-x-10-6-snow-leopard&#47;.  But that's all pretty overkill.  I have home-brew set up, with imagemagick and ghostscript and rmagick and everything installed.  I don't want to run some guy's script to re-install everything outside of home-brew.</p>
<p>Finally I find this http:&#47;&#47;superuser.com&#47;questions&#47;324980&#47;how-do-you-re-install-a-package-with-homebrew-mac, which helpfully includes the note 'Some tools will complain unless the ghostscript fonts are installed to &#47;usr&#47;local&#47;share&#47;ghostscript&#47;fonts'.  Yes! That is my problem!  But reinstalling imagemagick with fontconfig didn't solve that problem.</p>
<p>Then this guy http:&#47;&#47;stackoverflow.com&#47;questions&#47;7412208&#47;imagemagick-and-os-x-lion-trouble suggests building ImageMagick from source with the --with-gs-font-dir=&#47;usr&#47;local&#47;share&#47;ghostscript&#47;fonts.  Does that tell imagemagick where the fonts are?  Or does it put fonts there?  I'm trying...</p>
<blockquote><p>
 brew reinstall imagemagick --with-fontconfig --with-gs-font-dir=&#47;usr&#47;local&#47;share&#47;ghostscript&#47;fonts<br />
<&#47;blockquote></p>
<p>...not sure if home-brew passes along the arguments like that.  Appears not.</p>
<p>Wow, well, finally something worked.  Who knows how.  I still have no fonts in &#47;usr&#47;local&#47;share&#47;ghostscript.  I suspect the step that finally fixed things was, after installing imagemagick --with-fontconfig, uninstall the rmagick gem and re-installing it.</p>
