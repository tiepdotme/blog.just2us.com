---
id: 444
title: Pitfalls with XIB Deployment Target
date: 2010-09-30T23:36:23+00:00
author: Junda Ong
layout: post
guid: http://just2us.com/2010/09/pitfalls-with-xib-deployment-target/
permalink: /2010/09/pitfalls-with-xib-deployment-target/
dsq_thread_id:
  - 149194598
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400242417
categories:
  - Development
tags:
  - Xcode
---
I encountered a bug when installing my app on a device running iOS 3.x. The app runs fine with iOS 4.x, but crashed on iOS 3.x.

The error message is an NSUnknownKeyException encountered when the application main is run. 

> Terminating app due to uncaught exception &#8216;NSUnknownKeyException&#8217;, reason: &#8216;[<UIWindow 0x1451d0> setValue:forUndefinedKey:]: this class is not key value coding-compliant for the key rootViewController.&#8217;

After some digging, I found that it is to do with my Deployment Target of my MainWindow.xib file being set to **iOS 4**, when it should really be **All Versions of iOS**.

This happened when the project is created, and then I changed to _Project’s Deployment Target_ to iOS 3.0. Although the project’s specified iOS 3.0, all xib files will not automatically change its deployment target.

This is what I see when I change the deployment target to All Versions of iOS. 

<a href="http://just2us.com/wp-content/uploads/2010/09/XibDocumentInfo.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://just2us.com/wp-content/uploads/2010/09/XibDocumentInfo.png', '');"><img style="border-bottom: 0px; border-left: 0px; display: inline; border-top: 0px; border-right: 0px" title="Xib Document Info" border="0" alt="Xib Document Info" src="http://just2us.com/wp-content/uploads/2010/09/XibDocumentInfo_thumb.png" width="600" height="350" /></a>]

(To change xib info, in Interface Builder, go to Windows > Document Info)

What is good here is that once I changed to All Versions of iOS, Interface Builder will warn me of the issues. As it says, UIWindow does not have a rootViewController prior to iOS 4.0! Who knows that!?

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>