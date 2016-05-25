---
id: 351
title: 'What&rsquo;s new for SG 4D?'
date: 2010-03-28T12:43:07+00:00
author: Junda Ong
layout: post
guid: http://just2us.com/2010/03/whats-new-for-sg-4d/
permalink: /2010/03/whats-new-for-sg-4d/
dsq_thread_id:
  - 80054438
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400194746
categories:
  - Applications
  - iPhone
  - News
tags:
  - SG 4D
---
SG 4D <a href="http://blog.just2us.com/2010/03/sg-4d-v2/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/2010/03/sg-4d-v2/', 'version 2');">version 2</a> was released with _tons of changes_. It is a very exciting release, a big overhaul, and with lots of new features. 

In this post, I will highlight the significant changes for end-users. In the next post, I will talk about the changes from a technical perspective, which would include the new technologies that were used – CoreData, In-app-purchase, Facebook integration, etc..

&#160;

### How did we come thus far?

Before we start with the changes in the app, let’s look at a short history of the app. 

  * Oct 2008: SG 4D was <a href="http://www.just2me.com/2008/10/sg-4d.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.just2me.com/2008/10/sg-4d.html', 'first released');"><strong>first released</strong></a>, and it became the Top 100 apps instantly. 
  * Jul 2009: A minor bug fix, and it was also the **last update** for version 1. 
  * Nov 2009: SG 4D **<a href="http://blog.just2us.com/2009/11/sg-4d-now-on-android/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/2009/11/sg-4d-now-on-android/', 'for Android');">for Android</a>** was released. 
  * Jan 2010: SG 4D was squeezed <a href="http://blog.just2us.com/2010/01/sg-4d-is-no-longer-in-top-100/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/2010/01/sg-4d-is-no-longer-in-top-100/', 'out of Top 100');"><strong>out of Top 100</strong></a>. This is mainly due to a new and better 4D app arriving in App Store. 
  * Mar 2010: SG 4D <a href="http://blog.just2us.com/2010/03/sg-4d-v2/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/2010/03/sg-4d-v2/', 'v2 released');"><strong>v2 released</strong></a> 

It is interesting to note a few things about the history. There was very little update for SG 4D, and when there are updates, it is usually minor changes and bug fixes.. 

SG 4D dominated and remained as the only 4D app until 2 months ago, when <a href="http://live4d.sg/home.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://live4d.sg/home.html', 'SG Live 4D');">SG Live 4D</a> was released. SG Live 4D provided a very fun feature – live broadcast at 6.33pm! This is a huge competitive edge, and consumers choose SG Live 4D over SG 4D since then.

But note that SG 4D version 2 was not released because it lost the competitive edge, though that is a huge motivating factor. SG 4D version 2 for iPhone was planned to release after SG 4D <a href="http://blog.just2us.com/2009/11/sg-4d-now-on-android/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/2009/11/sg-4d-now-on-android/', 'for Android');">for Android</a>, which includes a major overhaul. You would see why later.

&#160;

<!--more-->


  


### Retrieving Latest Results Faster

The first improvement is to make the retrieval of the 4D results faster. 

In version 1, 4D results were retrieved from Singapore Pools server. That way was sometime slow due to the server having a high load, and also because the retrieval process was not optimized. In version 2, all the 4D results were retrieved via <a href="http://code.google.com/appengine/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://code.google.com/appengine/', 'Google’s cloud infrastructure');">Google’s cloud infrastructure</a>. 

<a href="http://blog.just2us.com/wp-content/uploads/2010/03/appengine_lowres.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/03/appengine_lowres.png', ' ');"><img title="appengine 4d" style="border-top-width: 0px; display: block; border-left-width: 0px; float: none; border-bottom-width: 0px; margin-left: auto; margin-right: auto; border-right-width: 0px" height="109" alt="appengine 4d" src="http://blog.just2us.com/wp-content/uploads/2010/03/appengine4d.png" width="240" border="0" /> </a>

This makes retrieval not only faster, but also more stable.

And similarly, SG 4D <a href="http://blog.just2us.com/2009/11/sg-4d-now-on-android/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/2009/11/sg-4d-now-on-android/', 'for Android');">for Android</a> retrieves results with the same architecture.

&#160;

### Email and SMS a Result

Users can now email or SMS a result of a particular day, informing friends of a result, or telling them they have strike lottery!

In fact, users can copy the result, and paste it in any apps eg. Facebook or twitter.

<p align="center">
  <img title="Actions" style="border-top-width: 0px; display: inline; border-left-width: 0px; border-bottom-width: 0px; margin: 0px 20px 0px 0px; border-right-width: 0px" height="244" alt="Actions" src="http://blog.just2us.com/wp-content/uploads/2010/03/Actions_thumb.png" width="164" border="0" /><a href="http://blog.just2us.com/wp-content/uploads/2010/03/SMS.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/03/SMS.png', '');"><img title="SMS" style="border-top-width: 0px; display: inline; border-left-width: 0px; border-bottom-width: 0px; margin: 0px 0px 0px 20px; border-right-width: 0px" height="244" alt="SMS" src="http://blog.just2us.com/wp-content/uploads/2010/03/SMS_thumb.png" width="164" border="0" /></a>&#160;
</p>

&#160;

### More Handicap Friendly

The app is now more friendly with VoiceOver turned on. The numbers are read out digit after digit with a slightly longer pause eg. _1-2-3-4._

&#160;

### 24 years of Past Results

In version 2, we have made available 24 years of past results since May 1986 (when <a href="http://en.wikipedia.org/wiki/4-Digits" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://en.wikipedia.org/wiki/4-Digits', 'betting was computerized');">betting was computerized</a>). 

 <img title="Past Results" style="border-top-width: 0px; display: block; border-left-width: 0px; float: none; border-bottom-width: 0px; margin-left: auto; margin-right: auto; border-right-width: 0px" height="244" alt="Past Results" src="http://blog.just2us.com/wp-content/uploads/2010/03/PastResults_thumb.png" width="164" border="0" />

_Disclaimer: You need to unlock the Premium Features ($3.99) to get 24 years of results. Without unlocking, only 3 years of results are available._

&#160;

### Checking Past Results Offline

Even better, we have made checking of the past results possible in offline mode! No longer do you need Internet to dig up a past result. 

&#160;

### Analyzing Number Better

Number Analysis is improved in many ways:

  * You can enter ‘R’ to represent any digit 
  * You can filter different prize category: Interested in 1st, 2nd, 3rd, starter or consolation? 
  * The analysis is done offline and no Internet is needed 
  * Its much faster, even with 24 years of data 
  * The results are shown neatly 
  * You can view the result for that draw, with your number in red 

<p align="center">
  <a href="http://blog.just2us.com/wp-content/uploads/2010/03/IMG_0508.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/03/IMG_0508.png', '');"><img title="IMG_0508" style="border-top-width: 0px; display: inline; border-left-width: 0px; border-bottom-width: 0px; margin: 0px 20px 0px 0px; border-right-width: 0px" height="244" alt="IMG_0508" src="http://blog.just2us.com/wp-content/uploads/2010/03/IMG_0508_thumb.png" width="164" border="0" /></a> <a href="http://blog.just2us.com/wp-content/uploads/2010/03/IMG_0509.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/03/IMG_0509.png', '');"><img title="IMG_0509" style="border-top-width: 0px; display: inline; border-left-width: 0px; border-bottom-width: 0px; margin: 0px 20px 0px 0px; border-right-width: 0px" height="244" alt="IMG_0509" src="http://blog.just2us.com/wp-content/uploads/2010/03/IMG_0509_thumb.png" width="164" border="0" /></a> <a href="http://blog.just2us.com/wp-content/uploads/2010/03/IMG_0510.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/03/IMG_0510.png', '');"><img title="IMG_0510" style="border-top-width: 0px; display: inline; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="244" alt="IMG_0510" src="http://blog.just2us.com/wp-content/uploads/2010/03/IMG_0510_thumb.png" width="164" border="0" /></a>
</p>

&#160;

### Removing Ad Banner

In version 1, there is always an ad banner at the bottom of the screen. Though no one has complained or requested for a ad-free version, we have made it possible to remove it.

In version 2, users may purchase and unlock Premium Features ($3.99) to remove the ad, and including other goodies.

&#160;

### Customizing your Lucky Wallpaper

We know you believe in auspicious number, auspicious outlet, and therefore probably an auspicious wallpaper. We do too ^^

<a href="http://blog.just2us.com/wp-content/uploads/2010/03/Wallpaper.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/03/Wallpaper.png', '');"><img title="Wallpaper" style="border-top-width: 0px; display: block; border-left-width: 0px; float: none; border-bottom-width: 0px; margin-left: auto; margin-right: auto; border-right-width: 0px" height="244" alt="Wallpaper" src="http://blog.just2us.com/wp-content/uploads/2010/03/Wallpaper_thumb.png" width="164" border="0" /></a>

&#160;

### More

There are a lot more things that we plan to put in the app to make 4D more fun. In future releases, you should find new features under More. 

For now, we would hope you can share with your friends and families <a href="http://sgresult.appspot.com/4d/download.jsp" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://sgresult.appspot.com/4d/download.jsp', 'SG 4D for iPhone');">SG 4D for iPhone</a>, and also <a href="http://sg4d.just2us.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://sg4d.just2us.com', 'for any other phones');">for any other phones</a>.

<img title="More" style="border-top-width: 0px; display: block; border-left-width: 0px; float: none; border-bottom-width: 0px; margin-left: auto; margin-right: auto; border-right-width: 0px" height="244" alt="More" src="http://blog.just2us.com/wp-content/uploads/2010/03/More_thumb.png" width="164" border="0" /></p> </p> </p> </p> </p> </p> 

Good luck, have fun and <a href="http://itunes.apple.com/sg/app/sg-4d/id294815815?mt=8" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://itunes.apple.com/sg/app/sg-4d/id294815815?mt=8', 'download the app');">download the app</a> (:

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>