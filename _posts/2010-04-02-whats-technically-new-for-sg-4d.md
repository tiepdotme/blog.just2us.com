---
id: 366
title: 'What&rsquo;s technically new for SG 4D?'
date: 2010-04-02T13:24:26+00:00
author: Junda Ong
layout: post
guid: http://just2us.com/2010/04/whats-technically-new-for-sg-4d/
permalink: /2010/04/whats-technically-new-for-sg-4d/
dsq_thread_id:
  - 81749235
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400154121
categories:
  - Applications
  - Development
  - iPhone
tags:
  - SG 4D
---
In the <a href="http://just2us.com/2010/03/whats-new-for-sg-4d/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://just2us.com/2010/03/whats-new-for-sg-4d/', 'previous post');">previous post</a>, I have highlighted what’s new for SG 4D. In this post, I will be highlighting what’s new, from a technical point of view.

I am excited to write what is technically new in the app, as there are aplenty, and we have used many awesome technology from iPhone 3.0 SDK, including CoreData, In-app purchase, Facebook Connect library, etc..

<!--more-->

### 1. Google’s AppEngine

I lied. Not only did we use awesome technology from iPhone, we used awesome technology from Google!

<img style="display: block; float: none; margin-left: auto; margin-right: auto;" src="http://blog.just2us.com/wp-content/uploads/2010/03/appengine4d.png" alt="" />

The server side is now completely powered by Google’s <a href="http://code.google.com/appengine/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://code.google.com/appengine/', 'AppEngine');">AppEngine</a>. This brings about several benefits: cheap/free server hosting, scalable architecture, stable+distributed+fast servers.

The process of retrieving 4D results is also technically more sound, using REST with JSON, and a proper cron job for web crawling. This makes me happier and sleeps better.

### 2. Core Data

Not only the server application is improved, the client application too, with another awesome technology!

In short, Core Data is the iPhone 3.0 SDK framework for managing data (or commonly databases). The list of features and benefits can be found <a href="http://developer.apple.com/iphone/library/documentation/Cocoa/Conceptual/CoreData/Articles/cdTechnologyOverview.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.apple.com/iphone/library/documentation/Cocoa/Conceptual/CoreData/Articles/cdTechnologyOverview.html', 'here');">here</a>.

What Core Data meant for SG 4D is that **all the results**, _I meant all 24 years of results_, are easily stored and queried using the framework.

No longer is your analysis of a 4D number done on the server side. When you asked to analysis a 4D number, your iPhone will query the large set of data using Core Data, and give you the analysis instantly!

This also means more advance analysis is possible in the future!

### 3. In-App Purchase

In-App Purchase is the ability to purchase items right from the app. This is a breakthrough for iPhone 3.0.

In SG 4D, you can now purchase/unlock the Premium Features immediately. Hence, it is not needed to download a lite version, and subsequently upgrading to a paid version.

<a href="http://blog.just2us.com/wp-content/uploads/2010/04/PurchasePremiumFeatures.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/04/PurchasePremiumFeatures.png', '');"><img style="display: inline; border: 0px;" title="Purchase Premium Features" src="http://blog.just2us.com/wp-content/uploads/2010/04/PurchasePremiumFeatures_thumb.png" border="0" alt="Purchase Premium Features" width="164" height="244" /></a>

We have also simplified the purchasing of the Premium Features by just having a $3.99 purchase to get all the features, including future features such as push notification!

### 4. Copy-and-paste

In iPhone 3.0, the _most awesome_ feature should be none other than copy-and-paste (pun intended).

In SG 4D, you could now copy and the 4D results, and paste it anywhere – SMS, Email, twitter, etc..

To make things easier, we also added functions to Email and SMS to your friends.

<a href="http://blog.just2us.com/wp-content/uploads/2010/04/Email.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/04/Email.png', '');"><img style="display: inline; margin: 0px 10px 0px 0px; border: 0px;" title="Email" src="http://blog.just2us.com/wp-content/uploads/2010/04/Email_thumb.png" border="0" alt="Email" width="164" height="244" /></a> <img style="margin: 0px 0px 0px 10px;" src="http://blog.just2us.com/wp-content/uploads/2010/03/SMS_thumb.png" alt="" />

### 5. Wallpaper Selection

You are now able to select your favorite wallpaper that goes along with the 4D results!

You might have noticed that the minimum OS requirement is now 3.1 (instead of 3.0). This is due to one of the SDK API we used for selecting, resizing and cropping your photo.

<a href="http://blog.just2us.com/wp-content/uploads/2010/04/Wallpaper.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/04/Wallpaper.png', '');"><img style="display: inline; border: 0px;" title="Wallpaper" src="http://blog.just2us.com/wp-content/uploads/2010/04/Wallpaper_thumb.png" border="0" alt="Wallpaper" width="164" height="244" /></a>

_Anyway, the photo above is my 3 hour old nephew, born on March 31, 2010 (Wed). And my dad strike 3rd prize, even before using him for wallpaper (:_

### 6. Sharing on Facebook

Facebook Connect for iPhone is a library for integrating apps with Facebook.

For SG 4D, you could now set your status to help to share SG 4D app with your friends. Right now, we know this is nothing much.

<a href="http://blog.just2us.com/wp-content/uploads/2010/04/Facebookpost.jpg" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/04/Facebookpost.jpg', '');"><img style="display: block; float: none; margin-left: auto; margin-right: auto; border: 0px;" title="Facebook post" src="http://blog.just2us.com/wp-content/uploads/2010/04/Facebookpost_thumb.jpg" border="0" alt="Facebook post" width="404" height="70" /></a>

In the future, we are thinking you could post status, such as “I strike 1st prize!”, “Bought 1234 for this wed, sat and sun”, etc.. If you have any idea on better use for Facebook with SG 4D, we are happy to hear.

### 7. Reviewing on AppStore

We would like you to review the app, no matter good or bad.

<a href="http://blog.just2us.com/wp-content/uploads/2010/04/Review.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/04/Review.png', '');"><img style="display: inline; border: 0px;" title="Review" src="http://blog.just2us.com/wp-content/uploads/2010/04/Review_thumb.png" border="0" alt="Review" width="164" height="244" /></a>

To help you to help us review, we have added a function under More to bring you right to App Store to write a review.

In addition, 14 days after you installed the app, SG 4D will prompt you to rate and review us.

### Conclusion

SG 4D version 2 is a big overhaul, technically more sound, and has promising future.

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>