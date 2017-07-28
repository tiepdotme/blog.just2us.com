---
id: 553
title: Wireless Ad Hoc Distribution for iPhone Apps
date: 2010-12-16T22:03:17+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=553
permalink: /2010/12/wireless-ad-hoc-distribution-for-iphone-apps/
dsq_thread_id:
  - 192093906
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400253414
categories:
  - Development
  - How-to
  - iPhone
tags:
  - Xcode
---
This post is for iPhone developers who need to send pre-released apps to (beta) testers.

For a long time since iOS development began, whenever developers need to send a pre-released app, testers need to go through a tedious process to install – they have to download, drag app to iTunes on a PC/Mac (NOT iPhone), and sync over USB..

Now with iOS 4, wireless installation is possible, right from an iPhone! 

This new process is much more convenient, or as convenient as installing from App Store. The result is that testers will be more glad to install and test your pre-released apps.

Jeffrey Sambells has a <a href="http://jeffreysambells.com/posts/2010/06/22/ios-wireless-app-distribution/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://jeffreysambells.com/posts/2010/06/22/ios-wireless-app-distribution/', 'good post');">good post</a> on how to create a little webpage that has links for testers to install the app. He even has a PHP script to conveniently skip some of the steps.

The post is helpful, but for myself, all I need is to a link that I can email to my testers. A link which they can simply click on and install the app wirelessly. 

I am going to explain how I do it my way.

&#160;

### Step 1 – Build and Archive

In Xcode, **Build and Archive** your Ad Hoc target.

Under Organizer window, select the archive app and select **Share** > **Distribute for Enterprise**. You will see this (screenshot from <a href="http://www.paradeofrain.com/2010/11/taking-the-pain-out-of-ad-hoc-testing/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.paradeofrain.com/2010/11/taking-the-pain-out-of-ad-hoc-testing/', 'paradeofrain');">paradeofrain</a>):

<p align="center">
  <img src="http://www.paradeofrain.com/wp-content/uploads/2010/11/appinfo.png" />
</p>

For the URL field, enter a temporary URL first (we will change that in step 2). This URL is the link to the IPA file which you will upload.

Press OK. You will now have the IPA file (the app) and a PLIST file (an XML that describes the app and where the IPA is).

&#160;

### Step 2 – Upload to Dropbox

Firstly, upload the IPA file to your <a href="https://www.dropbox.com/referrals/NTQxODM3Njk?src=global0" onclick="__gaTracker('send', 'event', 'outbound-article', 'https://www.dropbox.com/referrals/NTQxODM3Njk?src=global0', 'dropbox');">dropbox</a>. I prefer <a href="https://www.dropbox.com/referrals/NTQxODM3Njk?src=global0" onclick="__gaTracker('send', 'event', 'outbound-article', 'https://www.dropbox.com/referrals/NTQxODM3Njk?src=global0', 'dropbox');">dropbox</a>, but you may use a web server if you like. After the file is uploaded, get the dropbox public link for the IPA file. eg. <a href="http://dl.dropbox.com/u/1234/MyApp.ipa" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://dl.dropbox.com/u/1234/MyApp.ipa', 'http://dl.dropbox.com/u/1234/MyApp.ipa');" title="http://dl.dropbox.com/u/1234/MyApp.ipa">http://dl.dropbox.com/u/1234/MyApp.ipa</a>

Next, open the PLIST file and edit the url element. For example, 

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="xml" style="font-family:monospace;">...
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;key<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>url<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/key<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;string<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>http://dl.dropbox.com/u/1234/MyApp.ipa<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;string<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>
...</pre>
      </td>
    </tr>
  </table>
</div>



Upload the edited PLIST file to dropbox. Similarly, get the dropbox public link to the PLIST file. eg. <a href="http://dl.dropbox.com/u/1234/MyApp.plist" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://dl.dropbox.com/u/1234/MyApp.plist', 'http://dl.dropbox.com/u/1234/MyApp.plist');" title="http://dl.dropbox.com/u/1234/MyApp.ipa">http://dl.dropbox.com/u/1234/MyApp.plist</a>

&#160;

### Step 3 – Email Testers the Link

The secret to installing is this URI:

**itms-services://?action=download-manifest&url=http://dl.dropbox.com/u/1234/MyApp.plist** &#160;

Created a HTML email with a hyperlink pointing to the above URI. For example:

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="xml" style="font-family:monospace;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;a</span> <span style="color: #000066;">href</span>=”itms-services://?<span style="color: #000066;">action</span>=download-manifest&<span style="color: #000066;">url</span>=http://dl.dropbox.com/u/1234/MyApp.plist<span style="color: #000000; font-weight: bold;">&gt;</span></span>Download App<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/a<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></pre>
      </td>
    </tr>
  </table>
</div>



When a tester click on Download App from his iPhone, the installation will begin!

That’s it!

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>