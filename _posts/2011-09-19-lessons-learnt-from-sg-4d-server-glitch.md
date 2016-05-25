---
id: 689
title: Lessons learnt from SG 4D server glitch
date: 2011-09-19T22:40:45+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=689
permalink: /2011/09/lessons-learnt-from-sg-4d-server-glitch/
wp_plus_one_redirect:
  - 
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400154103
dsq_thread_id:
  - 419338405
categories:
  - Development
tags:
  - AppEngine
  - SG 4D
---
Last week, I upgraded Google&#8217;s App Engine to version 1.5.2.

I was careless and did not perform enough tests, and it turned out there is a bug with App Engine SDK 1.5.2 (I believe same with 1.5.0). There is a memcache error due to missing library.

If you encounter a "javax/cache/CacheException", then you are probably having the same problem. The fix is simply upgrading to the latest version at 1.5.4.

Over that 2 days where the bug infested the SG 4D app, I observed a few interesting behaviors. Here’s what I leant.

### Lesson 1: Ads revenue increased 10X

As the app could not display the latest results, users has nothing better to do, so they click the ads.. That resulted in 10X more clicks than usual!

An evil thought: Introduce glitches to drive ads revenue (just kidding!)

### Lesson 2: In-app-purchase increased 5X

The in-app-purchase to unlock the premium features increased too! Users thought that the app has “expired”, hence they can’t see the results, hence the purchase. 

(this hypothesis is true, and was validated by a couple of emails from users)

### Lesson 3: Other 4D apps rise quickly

The effect is immediate. On the first day that my app did not work, users downloaded alternatives. There are 2 other 4D apps, and they were both propelled to top 50! 

Surprisingly, my downloads remain the same. That means my downloads are constantly contributed by new users, and is unaffected by the bug.

### Lesson 4: Test, test, test!

Remember to test during software upgrade, even when it comes from Google!

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>