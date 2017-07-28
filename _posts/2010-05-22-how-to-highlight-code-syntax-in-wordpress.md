---
id: 384
title: How to highlight code syntax in WordPress
date: 2010-05-22T23:41:29+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=384
permalink: /2010/05/how-to-highlight-code-syntax-in-wordpress/
dsq_thread_id:
  - 98185822
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400252499
categories:
  - Development
  - How-to
tags:
  - wordpress
---
<a href="http://wordpress.org/extend/plugins/wp-syntax/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://wordpress.org/extend/plugins/wp-syntax/', 'WP-Syntax');">WP-Syntax</a> is the answer.

For example, this is how I highlight an iPhone’s Objective-C code in this post.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"><span style="color: #002200;">-</span> <span style="color: #002200;">&#40;</span><span style="color: #a61390;">void</span><span style="color: #002200;">&#41;</span>viewDidLoad   
<span style="color: #002200;">&#123;</span>    
    <span style="color: #002200;">&#91;</span>super viewDidLoad<span style="color: #002200;">&#93;</span>;    
    <span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span>title <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #400080;">NSString</span> stringWithFormat<span style="color: #002200;">:</span><span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"My %@ syntax"</span>, <span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"AWESOME"</span><span style="color: #002200;">&#93;</span>;    
    self.title <span style="color: #002200;">=</span> title;    
<span style="color: #002200;">&#125;</span></pre>
      </td>
    </tr>
  </table>
</div>

 
  
To use <a href="http://wordpress.org/extend/plugins/wp-syntax/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://wordpress.org/extend/plugins/wp-syntax/', 'WP-Syntax');">WP-Syntax</a>, simply surround the code with <pre lang=”LANGUAGE”> and </pre>, where LANGUAGE is the programming language.

To find out what to use for LANGUAGE, look under supported languages <a href="http://wordpress.org/extend/plugins/wp-syntax/other_notes/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://wordpress.org/extend/plugins/wp-syntax/other_notes/', 'here');">here</a>. </pre> </pre> 

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>