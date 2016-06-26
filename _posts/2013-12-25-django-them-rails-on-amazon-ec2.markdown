<!DOCTYPE html>
<html>
<head>
    
    <meta http-equiv="Content-Type" content="text/html" charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />

    
    <title>Django, then Rails on Amazon EC2</title>
    <meta name="description" content="" />

    <meta name="HandheldFriendly" content="True" />
    <meta name="MobileOptimized" content="320" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    
    <link rel="stylesheet" type="text/css" href="../assets/css/screen.css" />
    <link rel="stylesheet" type="text/css" href="http://fonts.googleapis.com/css?family=Droid+Serif:400,700,400italic|Open+Sans:700,400" />

    
    <meta name="generator" content="Ghost 0.3" />
<link rel="alternate" type="application/rss+xml" title="RSS" href="../rss/index.html">
</head>
<body class="post-template">

    
    



<main class="content" role="main">

    <article class="post">

        
        <header class="post-header">
            <a id="blog-logo" href="http://iancw.github.io">
                
                    iancw.github.io
                
            </a>
        </header>

        
        

        
        <span class="post-meta"><time datetime="2013-12-25">25 Dec 2013</time> </span>

        <h1 class="post-title">Django, then Rails on Amazon EC2</h1>

        <section class="post-content">
            <h3 id="background">Background</h3>

<p>I have used Amazon EC2 once before to host what turned out to be an exorbiantly priced personal minecraft server for my brother and I to play together on.  The current attempt will leverage the <em>free</em> tier.  While at it, I'm playing with github's blog feature.</p>

<h3 id="observations">Observations</h3>

<p>The <em>free tier</em> appears restricted to micro, featuring all 0.613 GB of RAM, "Very Low" network performance, and "EBS only" GB of hard drive space.</p>

<p>I had set up a previous key-pair on a different computer, but as I'm on vacation with only my laptop, I created a new key pair and downloaded the pem file. </p>

<p>As I went to set up billing alerts to receive emails if my <em>micro</em> instance beings costing me actual money, I see that my exorbiant minecraft server costs $0.99 per month to keep active.  This is not terrible, but is good to know.</p>

<h3 id="stepstosuccess">Steps To Success</h3>

<p>Now to ssh into my newly running instance, I followed the instructions at <a href='http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html'>http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html</a>.</p>

<p><code>chmod 400 my-key-pair.pem</code></p>

<p>I think attempted to ssh, but received 'Permission denied'. <br />
<code>ssh -i {pem file} {instance public DNS}</code></p>

<p>I checked my security groups and made sure ssh access was permitted from my ip.  Then I discovered that I hadn't supplied a username for ssh.  Amazon uses <code>ubuntu@{public DNS}</code> for ubuntu instance, <code>ec2-user@{...}</code> for amazon linux instances.  After supplying the proper user name I was able to connect over ssh.</p>

<p>I then installed git and cloned my repository.  I wasn't able to clone over the git protocol without an SSH key, but cloning over https worked.</p>

<p>The instance came with python 2.7.3 installed.</p>

<p>I installed pip <code>apt-get install python-pip</code>.</p>

<p>I installed Django with pip <code>pip install Django</code></p>

<p><code>python -c "import django; print(django.get_version())"</code> show django version 1.6.1.</p>

<p>I decided to try <code>python manage.py runserver</code> and visit <a href='http://[instance]:8000'>http://[instance]:8000</a> to see if I could view the development version from afar.  It didn't return anything.  It looks like I need to set up an Amazon security group to open port 8000 to the outside world.  But that didn't work either.</p>

<p>Man.  Django sucks.  All those hard-coded paths in the settings are ridiculous.  I'm going to change mountain weather to work with rails.  Now lets see if I can get a rails repo up and running on Amazon EC2.</p>

<ol>
<li>Install ruby1.8</li>
<li>Install rubygems</li>
<li>Remove ruby1.8</li>
<li>Install ruby1.9.3</li>
<li>Install rubygems (bah, this re-installs ruby1.8)</li>
<li>Remove ruby1.8</li>
</ol>

<p>(Might as well start with the latest)</p>

<p><code>ruby -v</code>: 1.9.3p0
<code>gem -v</code>: 1.8.11</p>

<ol>
<li><p>gem install rails</p>

<p><code>rails --version</code>: 4.0.2</p></li>
<li><p>apt-get install libsqlite3-dev</p></li>
<li><p>gem install sqlite3 -v '1.3.8'</p></li>
<li><p><code>rails blog</code></p></li>
<li><code>cd blog</code></li>
<li><code>bundle install</code> </li>
<li><code>apt-get install nodejs</code></li>
<li><code>rails server</code></li>
<li><em>SUCCESS!!!!!</em></li>
</ol>
        </section>

        <footer class="post-footer">

            
                <section class="author">
                    <h4>Ian Will</h4>
                    <p></p>
                </section>
            

            <section class="share">
                <h4>Share this post</h4>
                <a class="icon-twitter" href="http://twitter.com/share?text=Django, then Rails on Amazon EC2&url=http://iancw.github.io/django-then-rails-on-amazon-ec2/"
                    onclick="window.open(this.href, 'twitter-share', 'width=550,height=235');return false;">
                    <span class="hidden">Twitter</span>
                </a>
                <a class="icon-facebook" href="https://www.facebook.com/sharer/sharer.php?u=http://iancw.github.io/django-then-rails-on-amazon-ec2/"
                    onclick="window.open(this.href, 'facebook-share','width=580,height=296');return false;">
                    <span class="hidden">Facebook</span>
                </a>
                <a class="icon-google-plus" href="https://plus.google.com/share?url=http://iancw.github.io/django-then-rails-on-amazon-ec2/"
                   onclick="window.open(this.href, 'google-plus-share', 'width=490,height=530');return false;">
                    <span class="hidden">Google+</span>
                </a>
            </section>

        </footer>

        

    </article>

</main>

    <footer class="site-footer">
        <a class="subscribe icon-feed" href="http://iancw.github.io/rss/"><span class="tooltip">Subscribe!</span></a>
        <div class="inner">
             <section class="copyright">All content copyright <a href="../index.html">iancw.github.io</a> &copy; 2013 &bull; All rights reserved.</section>
             <section class="poweredby">Proudly published with <a class="icon-ghost" href="http://ghost.org">Ghost</a></section>
        </div>
    </footer>

    
    <script src="../shared/vendor/jquery/jquery.js"></script>

    
    <script type="text/javascript" src="../assets/js/index.js"></script>

</body>
</html>