---
id: 605
title: Introduction to API Business
date: 2011-05-23T09:02:00+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2011/05/introduction-to-api-business/
permalink: /2011/05/introduction-to-api-business/
dsq_thread_id:
  - 311100378
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400154751
categories:
  - API
---
<a href="http://apigee.com/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://apigee.com/', 'Apigee');">Apigee</a> has written a pretty comprehensive <a href="http://apigee.com/sites/default/files/documents/Is-Your-API-Naked.pdf" onclick="__gaTracker('send', 'event', 'download', 'http://apigee.com/sites/default/files/documents/Is-Your-API-Naked.pdf');">whitepaper on API business</a>. 

<p align="center">
  <a href="http://apigee.com/sites/default/files/documents/Is-Your-API-Naked.pdf" onclick="__gaTracker('send', 'event', 'download', 'http://apigee.com/sites/default/files/documents/Is-Your-API-Naked.pdf');"><img src="http://info.apigee.com/Portals/62317/images/whitepaper_naked1.png" /></a>
</p>

These are some good pointers from the whitepaper.

&#160;

##### 1. Understand the API users

Who are using the API? What are they using it for? How does it drive their business?

Not _all_ developers are your API users. 

&#160;

##### 2. API Key, Authentication & Authorization

API providers usually provide at least one of these:

  1. **Identity**: Who is making the request? This give birth to API Key. Google Maps uses that.
  2. **Authentication**: Are you really who you are? Twitter use username/password authentication via BasicAuth/OAuth/xAuth.
  3. **Authorization**: Are you allowed to do that for the user? Twitter also implement authorization for third party apps to do things in place for users.

The Role of OAuth is:

  * Solve app-to-app security problem
  * User grant access to app A to access app B, without sharing their actual password
  * User may revoke the access token at any time

Recommendations:

  * Use API Keys for non-sensitive (public) data
  * Use username/password for user-to-app
  * Use OAuth for server-to-server
  * SSL for everything

&#160;

##### 3. API Versioning

API changes and improves like a product, with new versions that are bound to come along in the future. Some of these API changes could be huge and might require a v2 or v3. eg. Google Maps API

Because developers using an older version might not be able to upgrade _their users_ instantly, the older version has to be supported during the transition.

&#160;

##### 4. Community and Audience

Developers, developers, developers.. it’s all about developers.

But first of all, you must have a cool product/API.

Then engage them in developer forums and events.



##### 5. API Metrics

Gauge your success by some metrics, such as:

  * Developer sign-ups
  * API traffic
  * Revenue

&#160;

##### 6. The VMSO

Like a product, be clear of the VMSO.

  * **Vision**: the dream
  * **Mission**: the everyday task to fulfill the dream
  * **Strategy**: the unique approach to take
  * **Objectives**: metrics to success

&#160;

##### 7. Target customer segment

What is the target customer segment? 

Are they the developers (web/mobile/etc), partners, or affiliate marketers? Stressing once again, it cannot be everyone.

&#160;

##### 8. Use cases

Develop use cases for your developers on how the API can be used.

This in terms let other developers grasp how they can use the API. 

&#160;

##### 9. Differentiate your API

In the same vertical, you have to differentiate yourself. 

API switching cost is often high, and difficult, so developers will avoid switching if there is no differentiated values.

&#160;

##### 10. Don&#8217;t try to market to developers

Developers are not enticed to marketing (gimmicks), because they think differently.

Instead, help them to solve their problems. Understand what is important to them and give them what they need to reach these goals.

Lastly, help them earn $

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>