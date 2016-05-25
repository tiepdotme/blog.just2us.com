---
id: 722
title: My THack (Hackathon) Experience
date: 2011-10-23T16:39:00+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2011/10/my-thack-hackathon-experience/
permalink: /2011/10/my-thack-hackathon-experience/
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400176499
dsq_thread_id:
  - 451057068
categories:
  - API
  - Development
  - Interesting
tags:
  - hackthon
---
<a href="http://blog.just2us.com/wp-content/uploads/2011/10/guidebnb-logo.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2011/10/guidebnb-logo.png', '');"><img style="background-image: none; border-bottom: 0px; border-left: 0px; margin: 0px 10px 0px 0px; padding-left: 0px; padding-right: 0px; display: inline; float: left; border-top: 0px; border-right: 0px; padding-top: 0px" title="guidebnb logo" border="0" alt="guidebnb logo" align="left" src="http://blog.just2us.com/wp-content/uploads/2011/10/guidebnb-logo_thumb.png" width="244" height="125" /></a>I participated in a 24hr hackathon over last weekend, and created Guidebnb – an app to find local guides. It is an <a href="http://devblog.hoiio.com/2011/10/guidebnb-airbnb-for-local-guides/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://devblog.hoiio.com/2011/10/guidebnb-airbnb-for-local-guides/', 'Airbnb for local guides');">Airbnb for local guides</a>.

If you want to try out, head over to <a href="http://guidebnb.just2us.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://guidebnb.just2us.com', 'http://guidebnb.just2us.com');">http://guidebnb.just2us.com</a>.

The whole hacking session was fun, and here are some random things I would like to share.

&#160;

### Setup your servers first

The hacking started at 10am, and we didn’t write a piece of code until 4pm! For 6 hours, we were merely setting up our server and development environment. We have a plan of what to use, but things didn’t work out. This is what we did:

  * The plan is to use <a href="http://heroku.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://heroku.com', 'Heroku');">Heroku</a> PHP. However, Heroku does <a href="http://killerapi.blogspot.com/2011/10/heroku-php-does-not-support-mongodb.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://killerapi.blogspot.com/2011/10/heroku-php-does-not-support-mongodb.html', 'not');">not</a> support MongoDB! (they supported eventually, a few days after the hackathon)
  * So we go for <a href="http://aws.amazon.com/ec2/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://aws.amazon.com/ec2/', 'Amazon EC2');">Amazon EC2</a>. We setup the instance, installed Apache. However, MongoDB has a dependency which could not be installed. (probably our fault)
  * So we go for <a href="http://www.slicehost.com/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.slicehost.com/', 'Slicehost');">Slicehost</a>. PHP and Mongo driver setup successfully. However, their PHP version is an older version (5.1), which caused some headache with Facebook API.

In the end, we settle for EC2 with MySQL.

&#160;

### SQL database has lots of boilerplate code

I hate SQL database, because they need too much setup. You need to create database, create table, design schema, then write complex SQL statements. You need to use <a href="http://www.pantz.org/software/mysql/mysqlcommands.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.pantz.org/software/mysql/mysqlcommands.html', 'mysql commands');">mysql commands</a>.

And when you need to add a column, you need to write SQL to add the column to the table, and also change all your affected SQL statements.

I have done that many times before, yet I am doing it again, all because the NoSQL-MongoDB could not be installed..

&#160;

### Facebook API is not that easy

<a href="http://developer.facebook.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.facebook.com', 'Facebook API');">Facebook API</a> is one of the widely used, yet also the also widely criticized API of all time.

It does give you problems, and high learning curve since there is a lot that you can do with it and you need to go figure it out yourself. They have non working examples too.

&#160;

### Hoiio & Expedia API are easy

We used 2 APIs

  * <a href="http://api.hoiio.com/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://api.hoiio.com/', 'Hoiio API');">Hoiio API</a> for SMS and IVR (Interactive Voice Responses) services
  * <a href="http://developer.ean.com/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.ean.com/', 'Expedia API');">Expedia API</a> for hotel search

Both are easy to use and do their stuff as intended. Took less than an hour to integrate the APIs.

&#160;

### I became a CSS ninja

I am a mobile developer, and API designer. 

I don’t dwell with web development and CSS stuff. However, for the hackathon, I have to do quite a bit of CSS. I started with a template that help start things. I typed a lot of inline CSS to solve things quickly. I used chrome developer tool and inspected elements one by one. I learnt stuff like <a href="http://css-tricks.com/551-can-we-prevent-css-caching/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://css-tricks.com/551-can-we-prevent-css-caching/', 'preventing CSS caching');">preventing CSS caching</a>.

I can write, but it is not my cup of tea.

&#160;

### Don’t change MAMP password

Being quirky about security, I changed the default password of my MAMP’s MySQL’s password. 

That is <a href="http://drupal.org/node/66187" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://drupal.org/node/66187', 'extra');">extra</a>, and that wasted 1 hour. (run into problems and ended up reinstalling MAMP)

&#160;

### 7 min presentation ain’t enough

When you have something cool and a lot to brag about, 7 min ain’t enough!

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>