---
id: 328
title: What to do if WordPress is not displaying UTF-8 correctly?
date: 2010-03-25T01:51:37+00:00
author: Junda Ong
layout: post
guid: http://just2us.com/2010/03/what-to-do-if-wordpress-is-not-displaying-utf-8-correctly/
permalink: /2010/03/what-to-do-if-wordpress-is-not-displaying-utf-8-correctly/
dsq_thread_id:
  - 79015750
arkayne-cache-post:
  - '<html><body></body></html>'
arkayne-time-post:
  - 1400244119
categories:
  - Development
  - How-to
tags:
  - wordpress
---
A while ago, this blog was not showing correctly some chinese (UTF-8) characters.

It was due to the WordPress that I have set up using a wrong character set. It was using latin1 instead of UTF-8.

To solve the problem, you could go to phpMyAdmin, and run the following SQLs.   
Note: Change wrdp1 to your wordpress database name accordingly.

<font face="Courier">ALTER TABLE wrdp1.wp_comments CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci; <br />ALTER TABLE wrdp1.wp_links CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci; <br />ALTER TABLE wrdp1.wp_options CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci; <br />ALTER TABLE wrdp1.wp_postmeta CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci; <br />ALTER TABLE wrdp1.wp_posts CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci; <br />ALTER TABLE wrdp1.wp_terms CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci; <br />ALTER TABLE wrdp1.wp_term_relationships CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci; <br />ALTER TABLE wrdp1.wp_term_taxonomy CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci; <br />ALTER TABLE wrdp1.wp_usermeta CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci; <br />ALTER TABLE wrdp1.wp_users CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci;</font> 

<a href="http://blog.just2us.com/wp-content/uploads/2010/03/phpmyadmin.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2010/03/phpmyadmin.png', '');"><img title="phpmyadmin" style="border-right: 0px; border-top: 0px; display: block; float: none; margin-left: auto; border-left: 0px; margin-right: auto; border-bottom: 0px" height="239" alt="phpmyadmin" src="http://blog.just2us.com/wp-content/uploads/2010/03/phpmyadmin_thumb.png" width="606" border="0" /></a>

The result should be like the table above. 

But note that we are not able to recover any UTF-8 characters that were in a post before this operation. You would need to edit the post, enter the correct UTF-8, and save.

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>