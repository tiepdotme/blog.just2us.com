---
id: 745
title: Find the real exception in Xcode debugger
date: 2012-02-04T14:55:58+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=745
permalink: /2012/02/find-the-real-exception-in-xcode-debugger/
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
  - 1400214737
dsq_thread_id:
  - 563976049
categories:
  - Development
  - iPhone
tags:
  - Xcode
---
There are times when you have exceptions raised in Xcode, but it breaks at UIApplicationMain in main(), and without giving you clues on where the error comes from.

There is a way to <a href="http://stackoverflow.com/questions/384775/how-do-i-find-out-what-exception-was-thrown-in-the-xcode-debugger-for-iphone/9138988#9138988" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://stackoverflow.com/questions/384775/how-do-i-find-out-what-exception-was-thrown-in-the-xcode-debugger-for-iphone/9138988#9138988', 'show more helpful debugging info');" target="_blank">show more helpful debugging info</a>.

Basically you need to set a breakpoint at `objc_exception_throw`.

If you are using Xcode 4.2, you can do the following:

  1. Go to Breakpoint Navigator pane (or press ⌘6)
  2. Click on the add icon on the bottom left
  3. Add symbolic breakpoint
  4. Enter `objc_exception_throw `for Symbol

Yeah. Find and burn those terrible bugs!

<a href="http://blog.just2us.com/wp-content/uploads/2012/02/add-symbolic-breakpoint-objc_exception_throw.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2012/02/add-symbolic-breakpoint-objc_exception_throw.png', '');"><img class="alignleft size-medium wp-image-746" title="add symbolic breakpoint objc_exception_throw" src="http://blog.just2us.com/wp-content/uploads/2012/02/add-symbolic-breakpoint-objc_exception_throw-300x94.png" alt="" width="300" height="94" srcset="http://blog.just2us.com/wp-content/uploads/2012/02/add-symbolic-breakpoint-objc_exception_throw-300x94.png 300w, http://blog.just2us.com/wp-content/uploads/2012/02/add-symbolic-breakpoint-objc_exception_throw.png 476w" sizes="(max-width: 300px) 100vw, 300px" /></a>

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>