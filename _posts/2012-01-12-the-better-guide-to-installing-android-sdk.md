---
id: 737
title: The Better Guide to Installing Android SDK
date: 2012-01-12T23:50:24+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=737
permalink: /2012/01/the-better-guide-to-installing-android-sdk/
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
  - 1400154513
dsq_thread_id:
  - 536305915
categories:
  - Android
  - Development
  - How-to
---
I wasn&#8217;t impressed with Android team on their documentation for <a href="http://developer.android.com/sdk/installing.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.android.com/sdk/installing.html', 'installing Android SDK');">installing Android SDK</a>. It is long, and jumps from page to page. Here is my better version:

&nbsp;

## Step 1 &#8211; Install Eclipse IDE

Go to <a href="http://www.eclipse.org/downloads/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.eclipse.org/downloads/', 'http://www.eclipse.org/downloads/');" target="_blank">http://www.eclipse.org/downloads/</a> and download Eclipse Classic (the latest version is 3.7.1).

After downloading, install and verify that it can run.

Note: If there is any error, check the <a href="http://developer.android.com/sdk/requirements.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.android.com/sdk/requirements.html', 'System Requirements');" target="_blank">System Requirements</a>. In particular, you might need to install the <a href="http://www.oracle.com/technetwork/java/javase/downloads/index.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.oracle.com/technetwork/java/javase/downloads/index.html', 'JDK');" target="_blank">JDK</a>.

&nbsp;

## Step 2 &#8211; Install Android SDK

Go to <a href="http://developer.android.com/sdk/index.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.android.com/sdk/index.html', 'http://developer.android.com/sdk/index.html');" target="_blank">http://developer.android.com/sdk/index.html</a> and download the Android SDK package.

For Mac and Linux users, download the zip/tgz package and unpack it to a safe location. The SDK files will be unpacked into a directory named _android-sdk-<machine-platform>_. Proceed to step (3).

For Windows users, download the **.exe** package, and run it to install. After installation is complete, the installation wizard will launch the **Android SDK and AVD Manager**. There is a slight inconsistent behaviour for Windows users here. Go to step (4) first, and return back to step (3) after you have finish step (4).

&nbsp;

## Step 3 &#8211; Install ADT Plugin

  1. Start Eclipse, select **Help** > **Install New Software**. Click **Add**.
  2. Enter &#8220;ADT Plugin&#8221; for _Name_ and the following for _Location_:
  
    **https://dl-ssl.google.com/android/eclipse/**
  3. Click **OK**
  4. Click **Next, **Next**, **Next****.. and **Finish**
  5. When the installation completes, restart Eclipse.
  6. In Eclipse, select **Window** > **Preferences** (Mac OS X: **Eclipse** > **Preferences**).
  7. Select **Android** from the left panel.
  8. For the _SDK Location_ in the main panel, click **Browse** and locate your downloaded SDK directory.
  9. Click **Apply**, then **OK**.

## 

## Step 4 &#8211; Adding Android Platforms

The Android SDK uses a modular structure that separates the major parts of the SDK. Specifically, the different versions of Android OS are each a module. To develop for a particular version, you would need to add the platform for that version.

To do so, from within Eclipse, select **Window > Android SDK and AVD Manager**.

<img class="alignnone" src="http://developer.android.com/images/sdk_manager_packages.png" alt="" width="560" height="443" />

Go to **Available Packages**, and select at least 1 platform. You may select additional platforms if you require.

Click **Install Selected** to download and install. Done!

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>