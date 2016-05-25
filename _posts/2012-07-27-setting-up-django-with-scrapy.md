---
id: 824
title: Setting up Django with Scrapy
date: 2012-07-27T20:56:17+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=824
permalink: /2012/07/setting-up-django-with-scrapy/
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
  - 1400253681
dsq_thread_id:
  - 782584449
categories:
  - Development
  - How-to
  - whatever
tags:
  - django
  - python
---
This guide is about using <a href="https://www.djangoproject.com/" onclick="__gaTracker('send', 'event', 'outbound-article', 'https://www.djangoproject.com/', 'Django');">Django</a>, the most popular Python **web framework**, and <a href="http://scrapy.readthedocs.org/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://scrapy.readthedocs.org/', 'Scrapy');">Scrapy</a>, the most popular Python **scraping framework**. Both of the frameworks are awesome, and they work very well standalone.

Before you continue reading, make sure you are already beyond &#8220;Getting Started&#8221; stage for both the frameworks.

At the end of the guide, what you can achieve is:

<cite>Run scrapy, and auto save the crawled items in Django ORM</cite>

### 1) Scrapy&#8217;s settings.py

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="python" style="font-family:monospace;"><span style="color: #ff7700;font-weight:bold;">def</span> setup_django_env<span style="color: black;">&#40;</span>path<span style="color: black;">&#41;</span>:
  <span style="color: #ff7700;font-weight:bold;">import</span> <span style="color: #dc143c;">imp</span><span style="color: #66cc66;">,</span> <span style="color: #dc143c;">os</span>
  <span style="color: #ff7700;font-weight:bold;">from</span> django.<span style="color: black;">core</span>.<span style="color: black;">management</span> <span style="color: #ff7700;font-weight:bold;">import</span> setup_environ
&nbsp;
  f<span style="color: #66cc66;">,</span> filename<span style="color: #66cc66;">,</span> desc <span style="color: #66cc66;">=</span> <span style="color: #dc143c;">imp</span>.<span style="color: black;">find_module</span><span style="color: black;">&#40;</span><span style="color: #483d8b;">'settings'</span><span style="color: #66cc66;">,</span> <span style="color: black;">&#91;</span>path<span style="color: black;">&#93;</span><span style="color: black;">&#41;</span>
 project <span style="color: #66cc66;">=</span> <span style="color: #dc143c;">imp</span>.<span style="color: black;">load_module</span><span style="color: black;">&#40;</span><span style="color: #483d8b;">'settings'</span><span style="color: #66cc66;">,</span> f<span style="color: #66cc66;">,</span> filename<span style="color: #66cc66;">,</span> desc<span style="color: black;">&#41;</span>       
&nbsp;
 setup_environ<span style="color: black;">&#40;</span>project<span style="color: black;">&#41;</span>
&nbsp;
  <span style="color: #808080; font-style: italic;"># Add django project to sys.path</span>
  <span style="color: #ff7700;font-weight:bold;">import</span> <span style="color: #dc143c;">sys</span>
  <span style="color: #dc143c;">sys</span>.<span style="color: black;">path</span>.<span style="color: black;">append</span><span style="color: black;">&#40;</span><span style="color: #dc143c;">os</span>.<span style="color: black;">path</span>.<span style="color: black;">abspath</span><span style="color: black;">&#40;</span><span style="color: #dc143c;">os</span>.<span style="color: black;">path</span>.<span style="color: black;">join</span><span style="color: black;">&#40;</span>path<span style="color: #66cc66;">,</span> <span style="color: #dc143c;">os</span>.<span style="color: black;">path</span>.<span style="color: black;">pardir</span><span style="color: black;">&#41;</span><span style="color: black;">&#41;</span><span style="color: black;">&#41;</span>
&nbsp;
setup_django_env<span style="color: black;">&#40;</span><span style="color: #483d8b;">'/path/to/django/myproject/myproject/'</span><span style="color: black;">&#41;</span></pre>
      </td>
    </tr>
  </table>
</div>

### 2) Scrapy&#8217;s items.py

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="python" style="font-family:monospace;"><span style="color: #ff7700;font-weight:bold;">from</span> scrapy.<span style="color: black;">contrib_exp</span>.<span style="color: black;">djangoitem</span> <span style="color: #ff7700;font-weight:bold;">import</span> DjangoItem
<span style="color: #ff7700;font-weight:bold;">from</span> myapp.<span style="color: black;">models</span> <span style="color: #ff7700;font-weight:bold;">import</span> Poll
&nbsp;
<span style="color: #ff7700;font-weight:bold;">class</span> PollItem<span style="color: black;">&#40;</span>DjangoItem<span style="color: black;">&#41;</span>:
    django_model <span style="color: #66cc66;">=</span> Poll</pre>
      </td>
    </tr>
  </table>
</div>

### 3) Scrapy&#8217;s pipelines.py

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="python" style="font-family:monospace;"><span style="color: #ff7700;font-weight:bold;">from</span> myapp.<span style="color: black;">models</span> <span style="color: #ff7700;font-weight:bold;">import</span> Poll
&nbsp;
<span style="color: #ff7700;font-weight:bold;">class</span> PollPipeline<span style="color: black;">&#40;</span><span style="color: #008000;">object</span><span style="color: black;">&#41;</span>:
&nbsp;
    <span style="color: #ff7700;font-weight:bold;">def</span> process_item<span style="color: black;">&#40;</span><span style="color: #008000;">self</span><span style="color: #66cc66;">,</span> item<span style="color: #66cc66;">,</span> spider<span style="color: black;">&#41;</span>:
&nbsp;
      item.<span style="color: black;">save</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span>
        <span style="color: #ff7700;font-weight:bold;">return</span> item</pre>
      </td>
    </tr>
  </table>
</div>

### Done!

That&#8217;s all to run scrapy and auto save the items to Django ORM. You can now run your regular

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="bash" style="font-family:monospace;">scrapy crawl myspider</pre>
      </td>
    </tr>
  </table>
</div>

PS: This guide serves to be complete. It adds to a popular <a href="http://stackoverflow.com/questions/4271975/access-django-models-inside-of-scrapy" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://stackoverflow.com/questions/4271975/access-django-models-inside-of-scrapy', 'Stackoverflow answer');">Stackoverflow answer</a>, and completes the picture for Django 1.4, which <a href="https://docs.djangoproject.com/en/dev/releases/1.4/#updated-default-project-layout-and-manage-py" onclick="__gaTracker('send', 'event', 'outbound-article', 'https://docs.djangoproject.com/en/dev/releases/1.4/#updated-default-project-layout-and-manage-py', 'Django adopts a new layout');">Django adopts a new layout</a>. And also provide the code for the <a href="http://doc.scrapy.org/en/0.14/experimental/djangoitems.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://doc.scrapy.org/en/0.14/experimental/djangoitems.html', 'experimental DjangoItem');">experimental DjangoItem</a> (rare!).

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>