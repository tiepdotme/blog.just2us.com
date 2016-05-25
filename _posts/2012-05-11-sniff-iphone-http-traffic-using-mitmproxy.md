---
id: 795
title: Sniff iPhone HTTP Traffic using mitmproxy
date: 2012-05-11T02:44:42+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=795
permalink: /2012/05/sniff-iphone-http-traffic-using-mitmproxy/
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
  - 1400254693
dsq_thread_id:
  - 684711736
categories:
  - Development
  - How-to
tags:
  - hack
  - tools
---
Sniffing traffic is a very hackish thing to do. So if you are against hacking things, stop reading.

There are a couple of ways to sniff the HTTP traffic. Using Wireshark, which has a nice user interface, is one of the mos popular ways. Today, I am going to introduce another tool call <a href="http://mitmproxy.org/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://mitmproxy.org/', 'mitmproxy');" target="_blank">mitmproxy</a>.

mitmproxy is an SSL-capable man-in-the-middle proxy. It was the very tool that was used to discover the <a href="http://mclov.in/2012/02/08/path-uploads-your-entire-address-book-to-their-servers.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://mclov.in/2012/02/08/path-uploads-your-entire-address-book-to-their-servers.html', 'misdeeds of Path');" target="_blank">misdeeds of Path</a>.

&nbsp;

### How to use mitmproxy?

  1. Download <a href="http://mitmproxy.org/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://mitmproxy.org/', 'mitmproxy');" target="_blank">mitmproxy</a>, and <a href="http://mitmproxy.org/doc/install.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://mitmproxy.org/doc/install.html', 'install');" target="_blank">install</a>. You could install from source and run `sudo python setup.py install`
  2. Go to your Terminal and run `mitmproxy`.
  3. Obtain the IP address of your computer by running `ifconfig en1` (or whatever that you are using).
  4. Set the proxy on your iPhone by going to your connected wifi settings. Set HTTP Proxy to “Manual”, and enter the IP of  your computer with port as 8080.
  5. Start sniffing! Refer to the <a href="http://mitmproxy.org/doc/mitmproxy.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://mitmproxy.org/doc/mitmproxy.html', 'console tool guide');" target="_blank">console tool guide</a>. Press &#8216;?&#8217; to bring up the list of commands.

<p style="text-align: center;">
  <img class="aligncenter" src="http://mitmproxy.org/doc/screenshots/mitmproxy.png" alt="" width="675" height="531" />
</p>

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>