---
id: 508
title: 'JDToaster &ndash; Android&rsquo;s Toaster for iPhone'
date: 2010-11-05T10:01:25+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=508
permalink: /2010/11/jdtoaster-androids-toaster-for-iphone/
robotsmeta:
  - index,follow
dsq_thread_id:
  - 167375803
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400154532
categories:
  - Development
  - iPhone
tags:
  - library
  - opensource
  - tutorials
---
One of the UI component that I like in Android is the <a href="http://developer.android.com/guide/topics/ui/notifiers/toasts.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.android.com/guide/topics/ui/notifiers/toasts.html', 'Toast Notification');">Toast Notification</a>. It is subtle, non-intrusive and fades away automatically. You simply call:

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="java" style="font-family:monospace;">Toast.<span style="color: #006633;">makeText</span><span style="color: #009900;">&#40;</span>context, “Hello Toaster <span style="color: #009900;">&#40;</span><span style="color: #339933;">:</span>”, <span style="color: #cc66cc;">5</span><span style="color: #009900;">&#41;</span>.<span style="color: #006633;">show</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></pre>
      </td>
    </tr>
  </table>
</div>

iPhone does not have an equivalent. It does have an Alert, but that is too intrusive.

As such, I created my own _Toaster class_. It was first used in <a href="http://blog.just2us.com/tag/sg-4d/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/tag/sg-4d/', 'SG 4D');">SG 4D</a>, 2 years ago, to show “No new results..” when user refreshed and there is no new results. That very first version was hastily created, with images used for the grey background.

2 years later, I improved my library. One of which is this Toaster class. I removed the images, and created the round radius programmatically.

It is a very simple class, which I wrote within minutes. I am open sourcing JDToaster and hosting it in <a href="https://github.com/samwize/JDToaster" onclick="__gaTracker('send', 'event', 'outbound-article', 'https://github.com/samwize/JDToaster', 'github public repos');">github public repos</a>.

## How to use JDToaster

1. Download the source form <a href="https://github.com/samwize/JDToaster" onclick="__gaTracker('send', 'event', 'outbound-article', 'https://github.com/samwize/JDToaster', 'https://github.com/samwize/JDToaster');" title="https://github.com/samwize/JDToaster">https://github.com/samwize/JDToaster</a>

2. Copy JDToasterView.h and JDToasterView.m to your project

3. To show a Toast, simply call

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"><span style="color: #002200;">&#91;</span>JDToasterView showToasterWithMessage<span style="color: #002200;">:</span><span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"Hello Toaster (:"</span> forDuration<span style="color: #002200;">:</span><span style="color: #2400d9;">5</span><span style="color: #002200;">&#93;</span>;</pre>
      </td>
    </tr>
  </table>
</div>

You will get something similar to this:

<p style="text-align: center;">
  <a href="http://blog.just2us.com/wp-content/uploads/2010/11/Screenshot-with-JDToaster1.jpg" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/11/Screenshot-with-JDToaster1.jpg', '');"><img class="aligncenter" style="background-image: none; padding-left: 0px; padding-right: 0px; display: inline; padding-top: 0px; border-width: 0px;" title="Screenshot-with-JDToaster" src="http://blog.just2us.com/wp-content/uploads/2010/11/Screenshot-with-JDToaster_thumb.jpg" border="0" alt="Screenshot-with-JDToaster" width="260" height="388" /></a>
</p>

That’s it!

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>