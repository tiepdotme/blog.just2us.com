---
id: 620
title: Play! Framework + App Engine Tutorial
date: 2011-07-09T10:30:00+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2011/07/play-framework-app-engine-tutorial/
permalink: /2011/07/play-framework-app-engine-tutorial/
dsq_thread_id:
  - 359366165
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400233058
categories:
  - Development
tags:
  - AppEngine
---
This is a tutorial: creating a barebone <a href="http://www.playframework.org/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.playframework.org/', 'Play! app');">Play! app</a> and deploying on the free <a href="http://code.google.com/appengine/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://code.google.com/appengine/', 'Google App Engine');">Google App Engine</a>. 

<p align="center">
  <img src="http://millad.net/img/playframework.png" width="206" height="64" /> <br /><img src="http://photos2.meetupstatic.com/photos/event/5/4/5/8/600_8721592.jpeg" width="205" height="225" />
</p>

## Steps to setting up Play! with App Engine

1. <a href="http://www.playframework.org/download" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.playframework.org/download', 'Download Play framework');">Download Play framework</a> (latest is 1.2.1)

2. Unzip and add path 

> export PATH=$PATH:/YOURPATH/play-1.2.1

3. <a href="http://www.playframework.org/modules/gae" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.playframework.org/modules/gae', 'Install GAE module');">Install GAE module</a> (latest is 1.4)

> play install gae 

4. <a href="http://www.playframework.org/modules/siena" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.playframework.org/modules/siena', 'Install siena module');">Install siena module</a> (latest is 1.5)

> play install siena 

5. Edit /YOURAPP/conf/dependencies.yml

> require:   
> &#160;&#160;&#160; &#8211; play   
> &#160;&#160;&#160; &#8211; play -> gae 1.4   
> &#160;&#160;&#160; &#8211; play -> siena 1.5

6. Add to conf/application.conf

> \# &#8212;- Google app engine module &#8212;-   
> module.gae=${play.path}/modules/gae-1.4   
> \# &#8212;- Siena module &#8212;-   
> module.siena=${play.path}/modules/siena-1.5 

7. Restart your app. GAE will start and a /war will be created

8. Edit /war/WEB-INF/appengine-web.xml and enter your appengine appid

9. Deploy

> play war MyFirstApp -o MyFirstApp-War   
> /Applications/eclipse/plugins/appengine-java-sdk-1.5.0/bin/appcfg.sh update MyFirstApp-War/

Go to <a href="http://yourapp.appspot.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://yourapp.appspot.com', 'http://yourapp.appspot.com');">http://yourapp.appspot.com</a>, and it should run!

Note: This tutorial is only a basic to getting a barebone Play! app to run on Google’s App Engine. Developing a Play! app on App Engine still require your effort. Here is an <a href="http://viralpatel.net/blogs/2011/01/first-play-framework-gae-siena-application-tutorial-example.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://viralpatel.net/blogs/2011/01/first-play-framework-gae-siena-application-tutorial-example.html', 'Easy Bookmark example');">Easy Bookmark example</a>.

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>