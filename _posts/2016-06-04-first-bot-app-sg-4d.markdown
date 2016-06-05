---
layout: post
title: "First Bot App - Didi for SG 4D"
author: Junda
date: 2016-06-04T15:10:37+08:00
tags: [SG 4D, Bot]
---

## Introducing _Didi_ the SG 4D Bot

_Didi_ is the name our SG 4D bot.

_Didi_ is capable of telling you the latest 4D results, or any other results since 1986!

[Start a chat](https://www.messenger.com/t/sgx4d/) on Facebook Messenger, or click the button below:

<div class="fb-messengermessageus col-lg-offset-4 col-lg-4 col-md-4 col-md-offset-4"
  messenger_app_id="102125519823247"
  page_id="1080193802040060"
  color="blue"
  size="xlarge" >
</div>

<br />

<script>
  window.fbAsyncInit = function() {
    FB.init({
      appId      : '102125519823247',
      xfbml      : true,
      version    : 'v2.6'
    });
  };

  (function(d, s, id){
     var js, fjs = d.getElementsByTagName(s)[0];
     if (d.getElementById(id)) {return;}
     js = d.createElement(s); js.id = id;
     js.src = "//connect.facebook.net/en_US/sdk.js";
     fjs.parentNode.insertBefore(js, fjs);
   }(document, 'script', 'facebook-jssdk'));
</script>

_This is the first version of our bot, so what Didi can understand is very limited now. But the more you talk to it, the more it will learn. So be patient and help Didi grow!_

<iframe width="420" height="315" src="https://www.youtube.com/embed/c4T1qM_D3nY" frameborder="0" allowfullscreen></iframe>


## On Facebook Bot Review

Following a [failed attempt](/2016/05/28/here-comes-a-new-gatekeeper-facebook-messenger-bot-reviewers/) with Facebook bot reviewer, SG 4D bot app was approved on second try!

Not so bad after all.

But I still have reservation seeing how the second reviewer test my bot. He did not re-test with _hello_ (which the bot failed to handle at first).

In fact he only [sent 2 messages](/img/sg4d-bot-second-review.png), and he is happy?
