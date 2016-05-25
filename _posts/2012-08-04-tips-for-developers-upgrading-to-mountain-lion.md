---
id: 841
title: Tips for Developers Upgrading to Mountain Lion
date: 2012-08-04T10:22:22+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=841
permalink: /2012/08/tips-for-developers-upgrading-to-mountain-lion/
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
  - 1400154051
dsq_thread_id:
  - 791789498
categories:
  - Development
  - How-to
tags:
  - mac
  - python
---
If you are a developer using Python for any purposes (warning: you could be using without knowing), do take heed.

<a href="http://blog.just2us.com/2012/07/mountain-lion-kills-my-python/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/2012/07/mountain-lion-kills-my-python/', 'Mountain Lion Kills Python');">Mountain Lion Kills Python</a>

As discussed in my previous post, upgrading to Mountain Lion will cause many of Python packages not to work. I have found out that /Library/Python/2.7/site-packages/ was cleared! The site-packages directory stores all the third party libraries that you have installed eg. virtualenv, django, pip, mysql, etc..

I have yet to understand the reason for Apple doing that warehouse clearance..

However, a tip for you:

If you are upgrading to Mountain Lion, backup /Library/Python/2.7/site-packages/ to Desktop first. After upgrading, you can copy site-packages back.

&nbsp;

_UPDATE:_

I also encountered missing path to mysql and mysql_config commands. Somehow PATH got altered. Here&#8217;s the fix:

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="shell" style="font-family:monospace;">export PATH=$PATH:/usr/local/mysql/bin/</pre>
      </td>
    </tr>
  </table>
</div>

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>