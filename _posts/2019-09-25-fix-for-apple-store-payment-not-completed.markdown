---
layout: post
title: "Fix for Apple Store 'Payment Not Completed'"
author: Junda
date: 2019-09-25T16:05:55+08:00
tags: [App Store]
---

We have observed that App Store frequently has an error when paying for an in-app purchase. We have a few [Dualgram](https://dualgram.com) users who have encountered the error at the point of purchase.

> Payment not completed

Or in Spanish:

> Pago no completado

![](/img/app-store-error-not-completed.jpg)

## The Fix

It turns out this got to do with Face ID bug.

Somehow, App Store abort the purchase.

A quick solution is to disable the use of Face ID for App Store purchases.

Go to Settings > Face ID & Passcode > disable for **iTunes & App Store**, then try to purchase again.

![](/img/app-store-disable-face-id.jpg)

If you're new here, check out our [latest camera app](/2019/09/17/we-made-an-app-to-record-front-and-back-cameras-simultaneously/) that records from multiple cameras on your iPhone!
