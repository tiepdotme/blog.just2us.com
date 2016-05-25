---
id: 608
title: Setting PATH variable in Mac permanently
date: 2011-05-30T08:59:00+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2011/05/setting-path-variable-in-mac-permanently/
permalink: /2011/05/setting-path-variable-in-mac-permanently/
dsq_thread_id:
  - 317853596
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400258587
categories:
  - How-to
tags:
  - bash
  - mac
---
This post I will highlight 3 ways to change to your <a href="http://linux.about.com/cs/linux101/g/path.htm" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://linux.about.com/cs/linux101/g/path.htm', 'PATH variable');">PATH variable</a>. 

&#160;

### 1. The quick way

Firstly, check your current PATH

> echo $PATH

If the directory (eg. _/my/new/path/_) you want to add is not already in your current PATH, then you can easily add with the command

> export PATH=$PATH:/my/new/path/

Done. Right?

It’s not really done, if you would like the PATH to change permanently (which is usually the case). This quick method only change the PATH for that bash session. If you close the terminal or open a new terminal, the PATH reverts back.

&#160;

### 2. Set permanently for a user

This brings us to the second way of setting PATH permanently for a user.

Edit the user’s bash profile (replace USERNAME)

> pico ~USERNAME/.bash_profile

Insert (or edit) this line

> PATH=$PATH:/my/new/path/

Press _ctrl-x_, then _ctrl-y_, to save the file.

Done.

&#160;

### 3. Set for all users

As a bonus, if you want the PATH to change for _all users_

> sudo pico /etc/paths

Enter your superuser password to edit, and insert or edit this link

> PATH=$PATH:/my/new/path/

That’s it! Enjoy your path!

&#160;

<a href="http://blog.just2us.com/wp-content/uploads/2011/05/beautiful-biking-path.jpg" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2011/05/beautiful-biking-path.jpg', '');"><img style="background-image: none; border-bottom: 0px; border-left: 0px; padding-left: 0px; padding-right: 0px; display: block; float: none; margin-left: auto; border-top: 0px; margin-right: auto; border-right: 0px; padding-top: 0px" title="beautiful biking path" border="0" alt="beautiful biking path" src="http://blog.just2us.com/wp-content/uploads/2011/05/beautiful-biking-path_thumb.jpg" width="603" height="454" /></a>

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>