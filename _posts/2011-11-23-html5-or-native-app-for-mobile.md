---
id: 725
title: HTML5 or Native App for mobile ?
date: 2011-11-23T23:53:29+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2011/11/html5-or-native-app-for-mobile/
permalink: /2011/11/html5-or-native-app-for-mobile/
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400154409
dsq_thread_id:
  - 481524736
categories:
  - Development
tags:
  - html5
  - mobile
---
This is a decision that mobile developers got to make when they develop an app.

There are pros and cons to both the platforms, and the decision largely depends on what you need to accomplish. These are the main factors.

<p align="center">
  <a href="http://blog.just2us.com/wp-content/uploads/2011/11/fruits-mixed.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2011/11/fruits-mixed.png', '');"><img style="display: inline" title="EDM" alt="EDM" src="http://blog.just2us.com/wp-content/uploads/2011/11/fruits-mixed_thumb.png" width="240" height="240" /></a>
</p>

  * Capabilities   
    The #1 factor would be the capabilities offered by the 2. Native App provides more integration with the mobile OS, and therefore can do much more. If you need access to address book, photo album, MP3, camera, etc, and accessing them is important to your app, then native app is a better choice. HTML5 is still pretty restricted, and is best for data-oriented web apps. 
  * User Experience   
    Native app provides native UI components from the OS, and that makes you feel like the app belongs to the OS itself. Native app also perform better, such as faster scrolling and switching views. HTML5 can provide more fanciful interfaces, largely because of the available JavaScript components. 
  * Where can it run   
    Native app must be built per mobile platform. So you got to build separately for iOS, Android, WP7, BlackBerry, etc. That means the same app built multiple times, with multiple programming languages and platform! HTML5 can be run on most new mobile platform. That is write once, run everywhere (but usually with some incompatibilities). 
  * Updates   
    Native app needs to be installed on the phone, and updating the software is controlled by the user, which means usually days or months before they do so. That is bad for critical bugs or rolling out of features. HTML5 on the other hand is instantaneous. 
  * Development Effort   
    Native app takes more time and more people with different skills on different platforms. It is also harder to code than HTML5. HTML5 is easier and faster develop.

However, you <a href="http://gigaom.com/2011/09/28/6-tips-for-entrepreneurs-from-mobilize-2011/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://gigaom.com/2011/09/28/6-tips-for-entrepreneurs-from-mobilize-2011/', 'don’t really need to pick sides');" target="_blank">don’t really need to pick sides</a>. A hybrid approach is possible, such as how Pandora does it. You can build a native app, which contains a webview that loads the HTML5 website (webview is a native app UI component such as <a href="http://developer.apple.com/library/ios/#documentation/uikit/reference/UIWebView_Class/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.apple.com/library/ios/#documentation/uikit/reference/UIWebView_Class/', 'iOS UIWebView');" target="_blank">iOS UIWebView</a>)!

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>