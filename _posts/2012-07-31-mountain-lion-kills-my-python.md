---
id: 832
title: Mountain Lion kills my Python
date: 2012-07-31T08:45:28+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=832
permalink: /2012/07/mountain-lion-kills-my-python/
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
  - 1400245758
dsq_thread_id:
  - 786232453
categories:
  - Development
tags:
  - mac
  - pitfall
  - python
---
I upgraded my Mac OS X to Mountain Lion (10.8) shortly after it was released.

Although I don&#8217;t believe it is worth upgrading, I still decided to be on &#8216;technology edge&#8217;.

Everything seems fine after about 2 hours of downloading and installing.. until the first kill.

I was working on Python and ran some commands. I did a pip install, and I got an error:

**<cite class="aligncenter">pkg_resources.DistributionNotFound: pip==1.1</cite>**

And virtualenv is also throwing error:

**<cite class="aligncenter">ImportError: No module named virtualenvwrapper.hook_loader</cite>**

After some googling, it can be easily fixed (thanks god) with:

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="shell" style="font-family:monospace;">sudo easy_install pip
sudo pip install virtualenv virtualenvwrapper</pre>
      </td>
    </tr>
  </table>
</div>

It seems like the Python site-packages were all gone too..

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>