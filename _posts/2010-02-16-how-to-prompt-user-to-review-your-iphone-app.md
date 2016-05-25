---
id: 283
title: How to prompt user to review your iPhone app
date: 2010-02-16T18:30:26+00:00
author: Junda Ong
layout: post
guid: http://just2us.com/2010/02/how-to-prompt-user-to-review-your-iphone-app/
permalink: /2010/02/how-to-prompt-user-to-review-your-iphone-app/
dsq_thread_id:
  - 67306374
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400240460
categories:
  - Development
  - How-to
  - iPhone
---
Apple’s app review is flawed – when users delete an app, it ask to rate. But if users like an app, it _does not_ ask to rate. That is bias.

If a user did not delete your app, it should not be a worthless app and should have a positive review. As a developer, we should prompt users to rate and comment an app after using it a number of times. 

<a href="http://txeet.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://txeet.com', '');"><img title="rate txeet" style="border-right: 0px; border-top: 0px; display: block; float: none; margin-left: auto; border-left: 0px; margin-right: auto; border-bottom: 0px" height="484" alt="rate txeet" src="http://just2us.com/wp-content/uploads/2010/02/ratetxeet.png" width="324" border="0" /></a>

&#160;

<!--more-->

What we can do is to detect that the app has started a number of times, and show a polite prompt to the user to ask him to rate the app. If user choose to rate the app, he will be redirected to App Store to rate and comment.

I am not directly providing the code to do that, as Arashpayan has done that excellently.

Arashpayan has written <a href="http://arashpayan.com/blog/index.php/2009/09/07/presenting-appirater/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://arashpayan.com/blog/index.php/2009/09/07/presenting-appirater/', 'Appirater');">Appirater</a> (read as Appi-rater). The code he provided at <a href="http://github.com/arashpayan/appirater/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://github.com/arashpayan/appirater/', 'http://github.com/arashpayan/appirater/');" title="http://github.com/arashpayan/appirater/">http://github.com/arashpayan/appirater/</a> works like a charm for <a href="http://txeet.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://txeet.com', 'txeet');">txeet</a>.

<p align="center">
  <a href="http://txeet.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://txeet.com', '&#160;');">&#160;</a>
</p>

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>