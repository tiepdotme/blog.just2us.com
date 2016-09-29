---
layout: post
title: "App Review Now Bans Facebook Single Sign-On"
header-img: /img/broken-apple.jpg
header-overlay: true
author: Junda
date: 2016-09-29T17:20:53+08:00
tags: [App Review]
---

A recent [Sep 2016 update](http://www.appstorereviewguidelineshistory.com/articles/2016-09-01-subscriptions-siri-kit-stickers/) to App Store Guidelines now adds the following:

> If your core app functionality is not related to a specific social network (e.g. Facebook, WeChat, Weibo, Twitter, etc.), you must provide access without a login or via another mechanism. Pulling basic profile information, sharing to the social network, or inviting friends to use the app are not considered core app functionality.

In other words, they are **rejecting** apps that use a social network for **only these purpose(s)**: account authentication, basic profile, sharing and inviting to friends.

To Apple, such purpose is not a strong case to use the social network!

As such, an update to [Jade app](http://jade2us.com) has been rejected.


## The Impact

What the app review team has introduced this time has very big impact to developers and the app ecosystem.

Many apps use popular social networks - Facebook/Twitter/Google - so that new users can sign up easily, without the need to create another password.

This convenient login mechanism is known as Single Sign-On (SSO).


## The _Solution_ Apple Wants

Apple suggest to either:

1. Create your own authentication system
2. Utilise the social network's core functionality


## What is _Core_?

It is subjective what is considered as _core functionality_.

In the case of Jade app, we feel Facebook is the most popular social network, and the fact that most people would have a Facebook account is a valuable functionality. But Apple thinks not.

We [asked](/img/app-review-sso-question.jpg) which of the following cases can be considered as core:

- Give read/write access to a Facebook friend to collaborate on a document?
- Access Facebook photos to use in the App?
- Post to Facebook Note app?

The [reply](/img/app-review-reject-sso.jpg) has no direct yes/no.

Instead, they provided these examples of utilising Facebook to create core functionality:

- Leverage Facebook's friends list API
- Leverage Facebook's shared interest API

We are ~~now~~ always at the mercy of Apple.

Hope we can have more [answers](http://stackoverflow.com/q/39432453/242682).