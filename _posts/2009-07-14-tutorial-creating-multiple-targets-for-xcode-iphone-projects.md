---
id: 122
title: How to create multiple targets for Xcode iPhone Projects
date: 2009-07-14T22:09:03+00:00
author: Junda Ong
layout: post
guid: http://just2us.com/2009/07/tutorial-creating-multiple-targets-for-xcode-iphone-projects/
permalink: /2009/07/tutorial-creating-multiple-targets-for-xcode-iphone-projects/
dsq_thread_id:
  - 65765110
arkayne-cache-post:
  - '<html><body></body></html>'
arkayne-time-post:
  - 1400247776
categories:
  - Development
  - How-to
  - iPhone
tags:
  - tutorials
---
If you want to build multiple versions of an application from a single Xcode project, you would want to cerate multiple targets. For example, when you want to release a free version and also a paid version, you should create 2 targets in that Xcode project. 

This tutorial will cover the how-to and the pitfalls in creating multiple targets.

&#160;

#### 1 Create a New Target

Lets assume we have an application call "Flowers", which is a paid version. And we would want to create a lite version that has some reduced functionality but is free. It is to note that both the paid version and lite version would share the same code, with only some differences.

Firstly, create a new target. Under Groups & Files, right click on Targets > Add > New Target&#160; (Figure 1 below). 

<p align="center">
  <a href="http://just2us.com//wp-content/uploads/2009/07/picture-1.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://just2us.com//wp-content/uploads/2009/07/picture-1.png', '');"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="249" alt="Figure 1" src="http://blog.just2us.com/wp-content/uploads/2009/07/picture-1-thumb.png" width="408" border="0" /></a>
</p>

Select Application as the new target template. 

Enter "FlowersLite" as the target&#8217;s name.

Pitfall: When a new target is added, it would not copy over any resources, compiled sources or libraries from the original target! You would need to copy them over manually (drag and drop from Flowers to FlowersLite). If you copy all correctly, you would see figure 2 below. The numbers in brackets indicate number of files, hence they should be the same for both the targets.

<p align="center">
  <img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="158" alt="Picture 5" src="http://blog.just2us.com/wp-content/uploads/2009/07/picture-5-thumb.png" width="244" border="0" />
</p>

&#160;

#### 2 Info.plist

We could define properties, such as application name and icon files, for each of the target. Figure 3 below shows "Flowers-Info.plist" for the full version.

<p align="center">
  <a href="http://just2us.com//wp-content/uploads/2009/07/picture-2.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://just2us.com//wp-content/uploads/2009/07/picture-2.png', '');"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="226" alt="Picture 2" src="http://blog.just2us.com/wp-content/uploads/2009/07/picture-2-thumb.png" width="560" border="0" /></a>
</p>

For the lite version, the "FlowersLite-Info.plist" could be changed as necessary. For example, the bundle identifier for the lite version could be "com.just2me.flowerslite" and the Icon file could be "Icon-lite.png" instead (as in figure 4 below).

<p align="center">
  <a href="http://blog.just2us.com/wp-content/uploads/2009/07/picture-3.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2009/07/picture-3.png', '');"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="174" alt="Picture 3" src="http://blog.just2us.com/wp-content/uploads/2009/07/picture-3-thumb.png" width="542" border="0" /></a>
</p>

&#160;

#### 3 Writing Preprocessor Codes

Preprocessor codes are used to determine which code would be used during compile time. You may want different targets to run different section of the codes using preprocessor codes. For illustration, we will add a LITE_VERSION definition to the lite version. 

Under Targets, right click FlowersLite > Get Info.

Change Configuration to "All Configurations" (this is important).

In the Preprocessor Macros field, add the flag LITE_VERSION (see figure 5 below). Note: If you don&#8217;t see the section "GCC 4.2 &#8211; Preprocessing", change the active SDK to base SDK and try again.

<p align="center">
  <a href="http://blog.just2us.com/wp-content/uploads/2009/07/picture-6.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2009/07/picture-6.png', '');"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="43" alt="Picture 6" src="http://blog.just2us.com/wp-content/uploads/2009/07/picture-6-thumb.png" width="520" border="0" /></a>
</p>

With the flag LITE_VERSION defined, we could now write codes that will be compiled for the different targets. An example is shown in figure 6 below.

<p align="center">
  <a href="http://blog.just2us.com/wp-content/uploads/2009/07/picture-7.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2009/07/picture-7.png', '');"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="135" alt="Picture 7" src="http://blog.just2us.com/wp-content/uploads/2009/07/picture-7-thumb.png" width="467" border="0" /></a>
</p>

When the active target is selected and being run, it will work and print correctly.

&#160;

### 4 Managing Resources

You could copy different resources (having same name but different) to the targets. Resource could refer to xib files, images, etc. 

For example, if the lite version has a different default loading screen, you could create another Default.png for the lite version. Note: To make it work, you have to copy the correct Default.png to that target&#8217;s "Copy Bundle Resources", and also to remove the incorrect Default.png.

&#160;

#### 5 Build for Distribution

When you are ready to compile the application for submission to iTunesconnect (release distribution), there is one last important thing worth checking.

It was pointed out in section 3 (Writing Preprocessor Code), that you have to change the configuration to "All Configurations" before you make any changes to the target properties (in this tutorial is adding the LITE_VERSION flag). That is important as the same flag is needed for all configurations, including distribution.

PS: I am stressing this last step as I had made this mistake.. and it resulted in my lite version being released as a paid version because the LITE_VERSION flag was only set for Debug, and not for Distribution!! I did not realize this mistake when compiling for Distribution, as I could only compile the app but not run it on simulator/device..

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>