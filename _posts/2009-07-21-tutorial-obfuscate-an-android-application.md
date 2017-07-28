---
id: 126
title: How to obfuscate an Android application
date: 2009-07-21T01:57:54+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2009/07/tutorial-obfuscate-an-android-application/
permalink: /2009/07/tutorial-obfuscate-an-android-application/
dsq_thread_id:
  - 65765114
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400239346
categories:
  - Android
  - Development
  - How-to
tags:
  - tutorials
---
There is no easy way to obfuscate Java classes of an Android app. This is no Eclipse plugin, nor even a working ant script.

Maybe there are <a href="http://code.google.com/p/zxing/source/browse/trunk/android-m3/build.xml?r=321" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://code.google.com/p/zxing/source/browse/trunk/android-m3/build.xml?r=321', 'working ant scripts');">working ant scripts</a>. But for Android SDK 1.5, it seems like no one has supplied a proper one, yet. And hence, I spent half a day hacking out <a href="http://blog.just2us.com/wp-content/uploads/2009/07/build.xml" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2009/07/build.xml', 'a script that works');">a script that works</a>. There are more effort and hurdles than what are presented here.. but for a simple working script, here it is how I did it:

&#160;

### 1 Create a Project

From the Terminal, in /android-sdk/tools/, run:

> ./android create project &#8211;target 2 &#8211;path /PATH/TO/ObfuscatedApp &#8211;activity MyActivity &#8211;package com.just2me.obfapp

&#160;

### 2 Edit build.xml

Replace the build.xml with <a href="http://blog.just2us.com/wp-content/uploads/2009/07/build.xml" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2009/07/build.xml', 'my modified build.xml');">my modified build.xml</a>, which is the most important item in this tutorial. The obfuscation work is in the optimize target as seen below.

<p align="center">
  <a href="http://blog.just2us.com/wp-content/uploads/2009/07/ant-buildxml.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2009/07/ant-buildxml.png', '');"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="214" alt="ant build.xml" src="http://blog.just2us.com/wp-content/uploads/2009/07/ant-buildxml-thumb.png" width="498" border="0" /></a>
</p>

Some points to note in the build.xml ant script:

  * Edit the properties for the path to your Android SDK and <a href="http://proguard.sourceforge.net/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://proguard.sourceforge.net/', 'Proguard');">Proguard</a>
  * If you use any libraries, copy them to /lib and add -libraryjars ${library-jar}/some\_lib\_used.jar accordingly 
  * -dontoptimize is needed for Android
  * For all classes that are declared in AndroidManifest.xml Application nodes (Activities, Receviers, etc), add an arg to tell proguard not to obfuscate. Exampe: "-keep public class com.just2me.obfapp.activity.*" 

&#160;

#### 3 Run ant

The last step is to simply run the ant script!

To package a debug version that is signed with a debug key, run "ant debug-obf".

To package a release version that is unsigned, run "ant release-obf".

If all is well, then you will find the products in /bin. ObfuscatedApp-debug.apk would be the debug package that could be installed on simulator/devices.

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>