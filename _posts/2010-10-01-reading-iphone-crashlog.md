---
id: 445
title: Reading iPhone Crashlog
date: 2010-10-01T01:07:00+00:00
author: Junda Ong
layout: post
guid: http://just2us.com/?p=445
permalink: /2010/10/reading-iphone-crashlog/
robotsmeta:
  - index,follow
dsq_thread_id:
  - 149203267
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400233006
categories:
  - Development
tags:
  - Xcode
---
I don’t have to discuss why you would want to read a crashlog.. it is just so much helpful than someone complaining “your app crashed”.

Reading iPhone’s crashlog is so much simple now. In the <a href="http://just2us.com/2010/02/how-to-read-iphone-crash-log/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://just2us.com/2010/02/how-to-read-iphone-crash-log/', 'past');">past</a>, you would need scripts to decipher the crashlogs. Since Xcode 3.2.2, the process is quite easy doing away with the scripts.

### 1. Get the crashlog first

To find the crashlog on your iPhone, or rather your user’s iPhone, they have to sync the device with their Mac/PC.

The crash logs can then be found from:

  * **Mac**:  /Library/Logs/CrashReporter/MobileDevice/
  * **Windows XP**: C:\Documents and Settings\Application Data\Apple computer\Logs\CrashReporter\
  * **Windows Vista**: C:\Users\[USERNAME]\AppData\Roaming\Apple computer\Logs\CrashReporter\MobileDevice\

### 2. Simply drag and drop to Xcode

If you open a crashlog, you will see a lot of function addresses. These does correspond to function names and line number, which in past you need to decipher with a script.

Now, you simple drag and drop the crashlog file to **Xcode > Organizer > Device Logs**.

Note: The deciphering only works if you have the app’s <a href="http://just2us.com/2010/02/how-to-read-iphone-crash-log/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://just2us.com/2010/02/how-to-read-iphone-crash-log/', 'valuable dSYM');">valuable dSYM</a>. If you archive your app with the latest version of Xcode, the app and it’s dSYM will be kept.

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>