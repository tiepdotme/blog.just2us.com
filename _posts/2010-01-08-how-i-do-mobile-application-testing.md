---
id: 233
title: How I do mobile application testing
date: 2010-01-08T01:01:03+00:00
author: Junda Ong
layout: post
guid: http://just2us.com/2010/01/how-i-do-mobile-application-testing/
permalink: /2010/01/how-i-do-mobile-application-testing/
dsq_thread_id:
  - 65765161
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400167661
categories:
  - Development
  - How-to
---
There are a lot of guides to general software testing methodologies, but there is a lack when it comes to **testing for mobile apps**.

Through the years I had with mobile application development, I have formed a habit of sort. It was always a _undocumented habit_, with improvements along the way.

When I read about <a href="http://cocoawithlove.com/2010/01/high-quality-in-software-development.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://cocoawithlove.com/2010/01/high-quality-in-software-development.html', 'QA without unit testing');">QA without unit testing</a>, it struck to me as a familiar process and methodology and I have used.

Therefore, here is my _documented habit_ on how I do mobile application testing. 

### 1. Unit Testing

Unit testing is the most frequently mentioned type of testing in software testing. That is because it is automated, and it is a good modular test on the methods/APIs. But a lot of time and cost could be wrongly spent on unit testing.

Instead, I choose to only do extensive test cases for very isolated and error-prone methods. And for all others, I would have only a few simple test cases, which serve more for the purpose of demonstrating how to use the methods.

Unit testing should be minimal for mobile application development, as a lot of mobile code comes from view controllers, which are unsuitable for unit testing.

&#160;

### 2. Sanity Testing

Sanity testing refers to testing the normal scenarios. It is use cases that normal users would encounter when using the mobile app. It includes the user interface that users would see and interact with.

Manually testing of each of the test cases is needed, and it is very important that these test cases and their steps are documented. A tester must follow the documented steps.

&#160;

### 3. Monkey Testing

Monkey testing covers the abnormal scenarios, or extreme cases. It is cases where a user would try to do unusual things with the app.

It is also essential to document these unusual test cases, but the steps need not be rigidly documented. 

Moreover, the tester should test like a monkey, trying to break or crash the app.

&#160;

### 4. Performance Testing

I always keep in mind:

> Engineering is about doing the best you can with limited resources

And mobile phones have very limited resources. It is very common to see mobile application crash or slowed to a crawl due to unforeseen scenarios that depletes resources. 

Performance testing is to test and ensure that the mobile app will stand the test of time..

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>