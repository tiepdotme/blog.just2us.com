---
id: 430
title: Building Your Own iPhone Static Library/Framework
date: 2010-08-11T01:16:11+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2010/08/building-your-own-iphone-static-libraryframework/
permalink: /2010/08/building-your-own-iphone-static-libraryframework/
dsq_thread_id:
  - 128192054
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400224691
categories:
  - Development
  - How-to
tags:
  - library
  - Xcode
---
It is good programmer practice to build your very own framework.

As a programmer, you would find certain tasks often the same across multiple projects. You might have experienced these before – writing (or copy-paste) the **same** code to perform certain function, creating projects using a **similar** framework/design, or reusing some **common** UI components. 

If you have experienced the above, it is a good time to build your own framework. 

There are many benefits to doing so:

  * Once you started your own framework, you would be more conscious of where a piece of code belongs to.
  * Maintaining and fixing the framework will benefit _all projects_ that use it.
  * You can send the static library and headers to others, without giving them the source code. This is also the same way <a href="http://developer.admob.com/wiki/IPhone" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.admob.com/wiki/IPhone', 'Admob');">Admob</a> and <a href="http://www.flurry.com/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.flurry.com/', 'Flurry');">Flurry</a> are sending their libraries to developers.
  * You will be able to test your framework and demo how to use it.

I have been wanting to build my own framework for a long time, but has been delaying.

But as I seek to create more iPhone apps in the coming days, I know I need to create my own framework to become more productive.

&#160;

## How to do so?

Firstly, the solution does not belong to me. 

I searched on the Internet on how to create your own framework, or static library, and there are a number of articles that came up. But I couldn’t find in _a single article_ for what I wanted.

I merely wanted 2 things:

  1. Create a project that encompass both a framework and a demo app.
  2. Simple and illustrated way to create a universal static library.

There are 2 separate articles that will achieve what I wanted, when combined. Hence, my guide here will simply be made up of 2 steps by following the 2 articles, and the final step on how to use the static library.

&#160;

## Step 1 – Create Project from a Static Library Template

Follow the instructions from <a href="http://jeffreysambells.com/iphone-os-static-library-template/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://jeffreysambells.com/iphone-os-static-library-template/', 'iPhone OS Static Library Template by Jeffrey Sambells');">iPhone OS Static Library Template by Jeffrey Sambells</a>. 

Jeffrey Sambells article is helpful as he provided a Xcode template, with clear instructions on how you can create your library. 

Not only does the template has a target for a static library, it also includes a target for building an iPhone app. This allows the programmer to create test cases for the static library and also demonstrating how to use the framework, all in the same project.

&#160;

## Step 2 – Creating a Universal Build

In Step 1, you would have created a project that builds your static library. 

You may follow the guide in Jeffrey Sambells’ article on how to use the static library (basically includes the project in another project), but there is a better way if you follow this step.

(There is a disadvantage if you follow the guide in Jeffrey Sambells’ article – you will not be able to distribute the static library to others.)

Instead, from the same project you created in Step 1, continue and follow the instructions from <a href="http://www.drobnik.com/touch/2010/04/universal-static-libraries/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.drobnik.com/touch/2010/04/universal-static-libraries/', 'Universal Static Library by Dr Touch');">Universal Static Library by Dr Touch</a>.

One important aspect of Dr Touch’s article is that it combines the library for both simulator and device, and merge them as a single universal build. In other words, it builds a fat binary that works for arm6, arm7 and i386 (for simulator). 

After following the instructions from Dr Touch’s article (working on the same project from Step 1), you should have a similar project structure to mine.

<img style="border-bottom: 0px; border-left: 0px; display: block; float: none; margin-left: auto; border-top: 0px; margin-right: auto; border-right: 0px" title="Xcode JDLibrary" border="0" alt="Xcode JDLibrary" src="http://blog.just2us.com/wp-content/uploads/2010/08/XcodeJDLibrary_thumb.png" width="391" height="510" />

&#160;

## Step 3 – Using the static library

To use the static library, find the ZIP file that is produced.

Unzip it, and place them in a project that you will be working on. Or send the ZIP file to a developer!

That’s it! 

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>