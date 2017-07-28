---
id: 426
title: Pitfall in using default values in settings bundle
date: 2010-08-01T00:00:12+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2010/08/pitfall-in-using-default-values-in-settings-bundle/
permalink: /2010/08/pitfall-in-using-default-values-in-settings-bundle/
dsq_thread_id:
  - 124465441
arkayne-cache-post:
  - '<html><body></body></html>'
arkayne-time-post:
  - 1400154415
categories:
  - How-to
tags:
  - pitfall
---
If you are implementing application settings using iPhone’s <a href="http://developer.apple.com/iphone/library/documentation/iphone/conceptual/iphoneosprogrammingguide/Preferences/Preferences.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.apple.com/iphone/library/documentation/iphone/conceptual/iphoneosprogrammingguide/Preferences/Preferences.html', 'Application Preferences');">Application Preferences</a>, then you will want to take note of this pitfall.

Referring to the <a href="http://developer.apple.com/iphone/library/documentation/PreferenceSettings/Conceptual/SettingsApplicationSchemaReference/Articles/PSTextFieldSpecifier.html#//apple_ref/doc/uid/TP40007011-SW1" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.apple.com/iphone/library/documentation/PreferenceSettings/Conceptual/SettingsApplicationSchemaReference/Articles/PSTextFieldSpecifier.html#//apple_ref/doc/uid/TP40007011-SW1', 'schema reference for PSTextFieldSpecifier');">schema reference for PSTextFieldSpecifier</a>, you would notice that there is a **DefaultValue** key. You might thought that this key is to return a default value, when the preference is not set.

In terms of code, you might thought that myvalue would return the default value.</p> 

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"><span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span>myvalue <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span><span style="color: #400080;">NSUserDefaults</span> standardUserDefaults<span style="color: #002200;">&#93;</span> stringForKey<span style="color: #002200;">:</span><span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"mykey"</span><span style="color: #002200;">&#93;</span></pre>
      </td>
    </tr>
  </table>
</div></p> 

But no, that is NOT the case. myvalue will always return nil, until you go to the Application Preferences page. In order to read a default value correctly, you will have to do more.

Refer to <a href="http://developer.apple.com/iphone/library/samplecode/AppPrefs/Introduction/Intro.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.apple.com/iphone/library/samplecode/AppPrefs/Introduction/Intro.html', 'AppPrefs Sample Code');">AppPrefs Sample Code</a> on how that can be done. The code is copied here for reference.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"> <span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span>testValue <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span><span style="color: #400080;">NSUserDefaults</span> standardUserDefaults<span style="color: #002200;">&#93;</span> stringForKey<span style="color: #002200;">:</span>kFirstNameKey<span style="color: #002200;">&#93;</span>;
 <span style="color: #a61390;">if</span> <span style="color: #002200;">&#40;</span>testValue <span style="color: #002200;">==</span> <span style="color: #a61390;">nil</span><span style="color: #002200;">&#41;</span>
 <span style="color: #002200;">&#123;</span>
   <span style="color: #11740a; font-style: italic;">// no default values have been set, create them here based on what's in our Settings bundle info</span>
   <span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span>pathStr <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span><span style="color: #400080;">NSBundle</span> mainBundle<span style="color: #002200;">&#93;</span> bundlePath<span style="color: #002200;">&#93;</span>;
   <span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span>settingsBundlePath <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span>pathStr stringByAppendingPathComponent<span style="color: #002200;">:</span><span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"Settings.bundle"</span><span style="color: #002200;">&#93;</span>;
   <span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span>finalPath <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span>settingsBundlePath stringByAppendingPathComponent<span style="color: #002200;">:</span><span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"Root.plist"</span><span style="color: #002200;">&#93;</span>;
    <span style="color: #400080;">NSDictionary</span> <span style="color: #002200;">*</span>settingsDict <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #400080;">NSDictionary</span> dictionaryWithContentsOfFile<span style="color: #002200;">:</span>finalPath<span style="color: #002200;">&#93;</span>;
   <span style="color: #400080;">NSArray</span> <span style="color: #002200;">*</span>prefSpecifierArray <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span>settingsDict objectForKey<span style="color: #002200;">:</span><span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"PreferenceSpecifiers"</span><span style="color: #002200;">&#93;</span>;
&nbsp;
    <span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span>firstNameDefault;
&nbsp;
    <span style="color: #400080;">NSDictionary</span> <span style="color: #002200;">*</span>prefItem;
   <span style="color: #a61390;">for</span> <span style="color: #002200;">&#40;</span>prefItem <span style="color: #a61390;">in</span> prefSpecifierArray<span style="color: #002200;">&#41;</span>
    <span style="color: #002200;">&#123;</span>
     <span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span>keyValueStr <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span>prefItem objectForKey<span style="color: #002200;">:</span><span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"Key"</span><span style="color: #002200;">&#93;</span>;
     <span style="color: #a61390;">id</span> defaultValue <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span>prefItem objectForKey<span style="color: #002200;">:</span><span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"DefaultValue"</span><span style="color: #002200;">&#93;</span>;
&nbsp;
      <span style="color: #a61390;">if</span> <span style="color: #002200;">&#40;</span><span style="color: #002200;">&#91;</span>keyValueStr isEqualToString<span style="color: #002200;">:</span>kFirstNameKey<span style="color: #002200;">&#93;</span><span style="color: #002200;">&#41;</span>
      <span style="color: #002200;">&#123;</span>
       firstNameDefault <span style="color: #002200;">=</span> defaultValue;
      <span style="color: #002200;">&#125;</span>
     <span style="color: #11740a; font-style: italic;">// Handle for other preferences you might have</span>
      <span style="color: #11740a; font-style: italic;">// ...</span>
    <span style="color: #002200;">&#125;</span>
&nbsp;
   <span style="color: #11740a; font-style: italic;">// since no default values have been set (i.e. no preferences file created), create it here   </span>
    <span style="color: #400080;">NSDictionary</span> <span style="color: #002200;">*</span>appDefaults <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #400080;">NSDictionary</span> dictionaryWithObjectsAndKeys<span style="color: #002200;">:</span>
                   firstNameDefault, kFirstNameKey,
                    <span style="color: #a61390;">nil</span><span style="color: #002200;">&#93;</span>;
   <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span><span style="color: #400080;">NSUserDefaults</span> standardUserDefaults<span style="color: #002200;">&#93;</span> registerDefaults<span style="color: #002200;">:</span>appDefaults<span style="color: #002200;">&#93;</span>;
   <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span><span style="color: #400080;">NSUserDefaults</span> standardUserDefaults<span style="color: #002200;">&#93;</span> synchronize<span style="color: #002200;">&#93;</span>;
  <span style="color: #002200;">&#125;</span>
&nbsp;
  <span style="color: #11740a; font-style: italic;">// we're ready to do, so lastly set the key preference values</span>
  firstName <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span><span style="color: #400080;">NSUserDefaults</span> standardUserDefaults<span style="color: #002200;">&#93;</span> stringForKey<span style="color: #002200;">:</span>kFirstNameKey<span style="color: #002200;">&#93;</span>;</pre>
      </td>
    </tr>
  </table>
</div>

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>