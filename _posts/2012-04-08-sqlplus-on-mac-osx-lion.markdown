---
layout: post
status: publish
published: true
title: Sqlplus on Mac OSX Lion
author:
  display_name: ian
  login: ian
  email: icwill@gmail.com
  url: http://iancwill.com/blog
author_login: ian
author_email: icwill@gmail.com
author_url: http://iancwill.com/blog
wordpress_id: 129
wordpress_url: http://iancwill.com/blog/?p=129
date: '2012-04-08 00:10:18 -0600'
date_gmt: '2012-04-08 04:10:18 -0600'
categories:
- Uncategorized
tags: []
comments: []
---
<p>For Mac OSX Lion, you need to download the 32 bit version of oracle sql-plus and instance client.  Put them in a common directory, which might look like...</p>
<blockquote><p>
iMac:share will$ ls -l &#47;usr&#47;local&#47;share&#47;oracle-client&#47;<br />
total 200864<br />
-rw-r--r--@ 1 x  staff       278 Apr  1  2009 BASIC_README<br />
-rw-r--r--@ 1 x  staff       282 Apr  1  2009 SQLPLUS_README<br />
-rwxr-xr-x  1 x  staff       593 Mar 27 22:43 call-sqlplus.sh<br />
-rwxr-xr-x  1 x  staff       567 Mar 27 22:39 call-sqlplus.sh~<br />
-r--r--r--@ 1 x  staff   1609607 Feb  2  2008 classes12.jar<br />
-rwxr-xr-x@ 1 x  staff     30556 Apr  1  2009 genezi<br />
-r-xr-xr-x@ 1 x  staff      1525 Aug 30  2004 glogin.sql<br />
-rwxr-xr-x  1 x  staff       331 Feb 10 20:20 launchscript.sh<br />
-rwxr-xr-x@ 1 x  staff  21537536 Mar 31  2009 libclntsh.dylib.10.1<br />
-rwxr-xr-x@ 1 x  staff   1683924 Feb 11  2009 libnnz10.dylib<br />
-rwxr-xr-x@ 1 x  staff   1142284 Feb 11  2009 libocci.dylib.10.1<br />
-rwxr-xr-x@ 1 x  staff  72626824 Apr  1  2009 libociei.dylib<br />
-rwxr-xr-x@ 1 x  staff    106184 Mar 25  2009 libocijdbc10.dylib<br />
-rwxr-xr-x@ 1 x  staff    106184 Mar 25  2009 libocijdbc10.jnilib<br />
-rwxr-xr-x@ 1 x  staff    933744 Mar 25  2009 libsqlplus.dylib<br />
-rwxr-xr-x@ 1 x  staff   1442316 Feb 11  2009 libsqlplusic.dylib<br />
-r--r--r--@ 1 x  staff   1555682 Feb  2  2008 ojdbc14.jar<br />
-rw-r--r--@ 1 x  staff        88 Mar 27 22:37 sqlnet.ora<br />
-rwxr-xr-x@ 1 x  staff     12612 Mar 25  2009 sqlplus<br />
-rw-r--r--@ 1 x  staff      1463 Apr  3 06:06 tnsnames.ora<br />
<&#47;blockquote></p>
<p>Then set the ORACLE_HOME and TNS_ADMIN environment variables, which could look like placing this in ~&#47;.profile.</p>
<blockquote><p>
export ORACLE_HOME=&#47;usr&#47;local&#47;share&#47;oracle-client<br />
export TNS_ADMIN=$ORACLE_HOME<br />
export DYLD_LIBRARY_PATH=$ORACLE_HOME:$DYLD_LIBRARY_PATH<br />
export PATH=$ORACLE_HOME:$PATH<br />
<&#47;blockquote></p>
<p>Edit tnsnames.ora to associate the correct ip address with a database name</p>
<blockquote><p>
yoursid =<br />
  (DESCRIPTION =<br />
    (ADDRESS_LIST =<br />
      (ADDRESS = (PROTOCOL = TCP)(HOST = ip.ip.ip.ip)(PORT = yourport))<br />
    )<br />
    (CONNECT_DATA =<br />
      (SERVICE_NAME = yoursid)<br />
    )<br />
  )<br />
<&#47;blockquote></p>
<p>Now (after source ~&#47;.profile) you should be able to call sqlplus user&#47;pw@sid.</p>
