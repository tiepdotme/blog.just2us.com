---
id: 381
title: How to resolve force close caused by Market
date: 2010-05-01T15:36:06+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2010/05/how-to-resolve-force-close-caused-by-market/
permalink: /2010/05/how-to-resolve-force-close-caused-by-market/
dsq_thread_id:
  - 91407606
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400188369
categories:
  - Android
  - How-to
---
This is an <a href="http://code.google.com/p/android/issues/detail?id=6579" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://code.google.com/p/android/issues/detail?id=6579', 'issue');">issue</a> where an application that is opened from Android’s Market might encounter a force close. <a href="http://txeet.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://txeet.com', 'txeet');">txeet</a> had the same issue:

<a href="http://blog.just2us.com/wp-content/uploads/2010/05/txeetforceclose.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/05/txeetforceclose.png', '');"><img title="txeet force close" style="border-right: 0px; border-top: 0px; display: block; float: none; margin-left: auto; border-left: 0px; margin-right: auto; border-bottom: 0px" height="484" alt="txeet force close" src="http://blog.just2us.com/wp-content/uploads/2010/05/txeetforceclose_thumb.png" width="292" border="0" /></a>&#160;

This is due to the application having two launcher components, and Market is confused and therefore not able to launch. Strangely, some phones do not face the same problem. 

Though this is a bug on Android side, the application can <a href="http://stackoverflow.com/questions/2244781/after-downloading-an-application-with-two-launcher-components-from-the-marketplac" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://stackoverflow.com/questions/2244781/after-downloading-an-application-with-two-launcher-components-from-the-marketplac', 'resolve');">resolve</a> by simply adding a line in the manifest file.

> <activity-alias android:name="com.android.internal.app.ResolverActivity" android:targetActivity=".Main" android:exported="true"/>

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>