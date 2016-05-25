---
id: 263
title: Pitfalls of NSFetchedResultsController
date: 2010-02-08T22:06:59+00:00
author: Junda Ong
layout: post
guid: http://just2us.com/2010/02/pitfalls-of-nsfetchedresultscontroller/
permalink: /2010/02/pitfalls-of-nsfetchedresultscontroller/
dsq_thread_id:
  - 65765179
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400221572
categories:
  - Development
tags:
  - CoreData
  - iPhone
  - tutorials
---
I have recently used one of the most useful framework in iPhone 3.0 – CoreData. 

There are many guides on using CoreData, such as from <a href="http://cocoadevcentral.com/articles/000086.php" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://cocoadevcentral.com/articles/000086.php', 'cocoadevcentral');">cocoadevcentral</a> or <a href="http://developer.apple.com/mac/library/documentation/Cocoa/Conceptual/CoreData/Articles/cdBasics.html#//apple_ref/doc/uid/TP40001650-TP1" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.apple.com/mac/library/documentation/Cocoa/Conceptual/CoreData/Articles/cdBasics.html#//apple_ref/doc/uid/TP40001650-TP1', 'Apple’s guide');">Apple’s guide</a>. But what I found lacking is that there was no discussion on the pitfalls of using CoreData, or its view controller, <a href="http://developer.apple.com/iphone/library/documentation/CoreData/Reference/NSFetchedResultsController_Class/Reference/Reference.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.apple.com/iphone/library/documentation/CoreData/Reference/NSFetchedResultsController_Class/Reference/Reference.html', 'NSFetchedResultsController');">NSFetchedResultsController</a>.

I learnt the pitfalls along the way, and there are 3 particular pitfalls that I would like to share with developers while developing <a href="http://txeet.com" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://txeet.com', 'txeet');">txeet</a> for iPhone.

&#160;

## 1. Performance hit with predicate using one-to-many relationship

When using NSFetchedResultsController, we would often form our predicate (like SQL) to retrieve some table rows. 

If you were to use a predicate that involves transversing a one-to-many relationship, the performance could be slowed down <a href="http://stackoverflow.com/questions/1145178/core-data-fetching-objects-that-are-in-relationship-to-another-object" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://stackoverflow.com/questions/1145178/core-data-fetching-objects-that-are-in-relationship-to-another-object', 'tremendously');">tremendously</a> (as slow as 30 sec to run, or even crash!). Take for example a **Template** model that has a one-to-many relationship **tags** to **Tag** model:

<a href="http://just2us.com/wp-content/uploads/2010/02/coredatapitfallcode1.jpg" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://just2us.com/wp-content/uploads/2010/02/coredatapitfallcode1.jpg', '');"><img title="coredata pitfall code1" style="border-top-width: 0px; display: inline; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="40" alt="coredata pitfall code1" src="http://just2us.com/wp-content/uploads/2010/02/coredatapitfallcode1_thumb.jpg" width="624" border="0" /></a>&#160; 

The predicate above would require transversing to each Tag to find ‘love’. This is computationally _very expensive_. 

The solution to this is to avoid transversing relationship. A faster way that CoreData could execute is to access the properties/attributes. For the above example, what I did is to add another attribute **tagsAsAttribute** to **Template** model. This property would store the tag names in a delimited format such as “;love;jokes;quotes;”. The predicate would then be changed to:

<a href="http://just2us.com/wp-content/uploads/2010/02/coredatapitfallcode2.jpg" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://just2us.com/wp-content/uploads/2010/02/coredatapitfallcode2.jpg', '');"><img title="coredata pitfall code2" style="border-top-width: 0px; display: inline; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="31" alt="coredata pitfall code2" src="http://just2us.com/wp-content/uploads/2010/02/coredatapitfallcode2_thumb.jpg" width="679" border="0" /></a> 

Note: This is not the best way to design the data model, as **tagsAsAttribute** has a dependency and is redundant.

&#160;

## 2. User-driven updates

If you read the <a href="http://developer.apple.com/iphone/library/documentation/CoreData/Reference/NSFetchedResultsControllerDelegate_Protocol/Reference/Reference.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.apple.com/iphone/library/documentation/CoreData/Reference/NSFetchedResultsControllerDelegate_Protocol/Reference/Reference.html', 'Apple’s guide to NSFetchedResultsControllerDelegate');">Apple’s guide to NSFetchedResultsControllerDelegate</a>, please note of the section User-Driven Updates.

In short, if you have user-driven updates, you should write the following as the first line in every (only one is shown below) of the NSFetchedResultsControllerDelegate delegate methods:

<a href="http://just2us.com/wp-content/uploads/2010/02/coredatapitfallcode3.jpg" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://just2us.com/wp-content/uploads/2010/02/coredatapitfallcode3.jpg', '');"><img title="coredata pitfall code3" style="border-top-width: 0px; display: inline; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="37" alt="coredata pitfall code3" src="http://just2us.com/wp-content/uploads/2010/02/coredatapitfallcode3_thumb.jpg" width="557" border="0" /></a> 

And when there is a user-driven update, set the **isStillUpdating** boolean to true, and set false when the update is completed.

User-driven updates could be re-ordering of table rows, or inserting of objects.

&#160;

## 3. abort() should NEVER be used in release

If you have used the sample code for CodeData, there is a line of code which is there only for testing environment. In the comments, it warned developers that **abort()** should not be used in shipping application..

But I didn’t read the comments..

Apparently, certain devices will occasionally have error when running certain CoreData methods. Eg. NSManagedObjectContext’s save. When there is an error, we could optionally handle the error, but we should NEVER abort and exit the app.

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>