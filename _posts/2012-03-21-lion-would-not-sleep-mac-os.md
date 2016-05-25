---
id: 761
title: Lion Would Not Sleep (Mac OS)
date: 2012-03-21T08:10:32+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=761
permalink: /2012/03/lion-would-not-sleep-mac-os/
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
  - 1400154241
dsq_thread_id:
  - 618615935
categories:
  - How-to
tags:
  - mac
  - pitfall
---
Not sure since which update, my Mac OS Lion 10.7 would not go into sleep mode.

Apparently, you can find out which service is <a href="http://blog.graceabundant.com/archives/2011/08/mac-osx-lion-not-sleeping/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.graceabundant.com/archives/2011/08/mac-osx-lion-not-sleeping/', 'preventing');" target="_blank">preventing</a> your Mac from sleeping by executing the bash command:

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="bash" style="font-family:monospace;">pmset <span style="color: #660033;">-g</span> assertions</pre>
      </td>
    </tr>
  </table>
</div>

This is the result for me:

<a href="http://blog.just2us.com/wp-content/uploads/2012/03/lion-wont-sleep.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2012/03/lion-wont-sleep.png', '');"><img class="wp-image-762 aligncenter" title="lion wont sleep" src="http://blog.just2us.com/wp-content/uploads/2012/03/lion-wont-sleep.png" alt="" width="433" height="202" /></a>

What&#8217;s wrong here is this: **PreventSystemSleep named: &#8220;org.cups.cupsd&#8221;**. That process is preventing my Lion from sleeping. If I kill the process, it just comes back up again.

The fix for me is to go to Preferences > Print & Scan > Delete my printer, then add again. This somehow triggers the system to really OFF printer sharing.

Insomnia solved.

&nbsp;

UPDATE: Another possible cause could be that the printer has a pending print job. Delete the print job, and the process will terminate.

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>